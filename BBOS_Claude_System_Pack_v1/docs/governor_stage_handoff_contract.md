# BBOS Governor–Stage Handoff Contract
@@DOC:BBOS_HANDOFF_CONTRACT@@

**Purpose:** Define the exact mapping between a stage skill's `<decision>` output and the governor's `<recommendation>` output. Without this, the governor cannot mechanically translate stage results into operator instructions.

---

## The handoff chain

Every command execution follows this sequence:

```
Operator command
  → Governor resolves active stage + command
    → Stage skill executes + returns <bbos_stage_output>
      → Validators run + return <bbos_validator_output> (one per validator)
        → Governor reads stage decision + all validator results
          → Governor issues <bbos_governor_output> with final recommendation
```

The governor **never skips this chain**. It does not issue a recommendation before the stage skill and required validators have returned results.

---

## Stage decision → Governor recommendation mapping

| Stage `<decision>` | All required validators | Governor `<recommendation>` | Operator meaning |
|---|---|---|---|
| `ready` | All `pass` | `advance` | Stage is complete. Move to next stage. Update state.json: `routing_status: advance`. |
| `ready` | One or more `fail` | `patch` | Stage work is done but a validator found issues. Fix the specific flagged items before advancing. |
| `ready` | One or more `not_run` | `remain` | Required validators have not been run. Run them before an ADVANCE recommendation can be issued. |
| `not_ready` | Any | `remain` | Stage work is incomplete. Continue working in the active stage. |
| `not_ready` + specific section identified | Any | `patch` | Stage work is mostly complete but a named section needs revision. Use PATCH command targeting that section. |
| `no_ship` | Any | `no_ship` | Required inputs are missing or a blocking condition exists. Do not proceed. Governor lists what is needed. |

### The `not_ready` → `remain` vs `patch` distinction

`remain` means: continue working broadly. Multiple things are incomplete or unclear.
`patch` means: one specific named output or section is the only thing blocking readiness. Everything else is complete.

The governor must not issue `patch` when more than one section is incomplete or when the nature of the incompleteness is unclear. In ambiguous cases, issue `remain` with the most important blocking issue named first in `<required_actions>`.

---

## Validator batch reading rule

When multiple validators run in the same command execution, the governor reads them as a batch:

- If ALL required validators return `pass` → validator batch = `all_pass`
- If ANY required validator returns `fail` → validator batch = `has_failures` → governor issues `patch` with each failing validator's findings summarised in `<required_actions>`
- If ANY required validator returns `not_run` → validator batch = `incomplete` → governor issues `remain` and lists which validators still need to run

The governor produces a single consolidated `<validator_results>` block summarising all validators run in that execution. Format:

```xml
<validator_results>
  <validator name="bbos-glabel-auditor">pass|fail|not_run</validator>
  <validator name="bbos-truth-gate-validator">pass|fail|not_run</validator>
  <validator name="bbos-stage-completeness-checker">pass|fail|not_run</validator>
</validator_results>
```

---

## PATCH command behavior at the stage level

When the active command is PATCH:

1. The operator must name the specific output or section being patched.
2. The stage skill modifies **only** the named item. All other sections of the asset pack are passed through unchanged.
3. The stage skill's `<updated_asset>` returns the **complete asset pack** with the patch applied — not just the patched section in isolation. This ensures the operator always has a complete, coherent document after every PATCH.
4. After a PATCH, the governor re-runs only the validators directly relevant to the patched section, not the full validator suite (unless the operator explicitly requests a full re-validation).
5. The governor's recommendation after a clean PATCH on the final blocking issue is `advance` — provided no new validator failures are introduced.

**Partial-patch output note:** The `<updated_asset>` tag carries the full asset pack post-patch. This is intentional. Do not return only the changed section — the operator needs a complete, coherent document they can save and use as the new version.

---

## State update responsibility

The governor's output ends every execution. The operator is responsible for updating `state.json` to reflect the governor's recommendation before the next session. The governor does not write state directly — it issues the recommendation; the operator writes the state.

Recommended `routing_status` values to set after each governor recommendation:

| Governor recommendation | Set `routing_status` to |
|---|---|
| `advance` | `advance` |
| `remain` | `remain` |
| `patch` | `patch` |
| `no_ship` | `no_ship` |

---

*This contract supersedes any implied handoff behavior described elsewhere in the pack. If another file contradicts this one, this file governs.*
