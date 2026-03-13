# BBOS Validator Batch Output Schema
@@DOC:BBOS_VALIDATOR_BATCH_SCHEMA@@

**Purpose:** When multiple validators run in a single command execution, each returns its own `<bbos_validator_output>` block. The governor requires a consolidated wrapper to mechanically determine the batch result without parsing natural language. This schema defines that wrapper.

---

## Schema definition

```xml
<bbos_validator_batch_output>
  <stage>03_OFR | 04_OUT | 05_SAL | ...</stage>
  <batch_status>all_pass | has_failures | incomplete</batch_status>
  <validators>
    <validator name="bbos-glabel-auditor" status="pass|fail|not_run"/>
    <validator name="bbos-truth-gate-validator" status="pass|fail|not_run"/>
    <validator name="bbos-stage-completeness-checker" status="pass|fail|not_run"/>
    <validator name="bbos-scarcity-checker" status="pass|fail|not_run"/>
  </validators>
  <consolidated_findings>
    <finding validator="bbos-glabel-auditor">
      <location>...</location>
      <issue>...</issue>
      <required_fix>...</required_fix>
    </finding>
    <finding validator="bbos-truth-gate-validator">
      <location>...</location>
      <issue>...</issue>
      <required_fix>...</required_fix>
    </finding>
    <!-- One <finding> block per failing issue across all validators.
         Pass results produce no <finding> entries. -->
  </consolidated_findings>
  <governor_recommendation_basis>advance | patch | remain | no_ship</governor_recommendation_basis>
</bbos_validator_batch_output>
```

---

## Batch status rules

| Condition | `batch_status` value |
|---|---|
| All required validators ran and all returned `pass` | `all_pass` |
| All required validators ran and at least one returned `fail` | `has_failures` |
| One or more required validators have not yet run (`not_run`) | `incomplete` |

## Governor recommendation derived from batch status

| `batch_status` | Stage `<decision>` | Governor recommendation |
|---|---|---|
| `all_pass` | `ready` | `advance` |
| `has_failures` | any | `patch` |
| `incomplete` | any | `remain` (validators must run before ADVANCE is possible) |
| `all_pass` | `not_ready` | `remain` (validators passed but stage work is incomplete) |

---

## Usage

The governor wraps all individual `<bbos_validator_output>` blocks inside a single `<bbos_validator_batch_output>` before issuing its final recommendation. Individual validator output blocks are preserved in full below the batch wrapper for operator reference.

**Output order in governor response:**
1. `<bbos_governor_output>` — routing decision and recommendation
2. `<bbos_validator_batch_output>` — consolidated validator summary
3. Individual `<bbos_validator_output>` blocks — full detail per validator

---

## Example — Stage 03 OFR, two validators pass, one fails

```xml
<bbos_validator_batch_output>
  <stage>03_OFR</stage>
  <batch_status>has_failures</batch_status>
  <validators>
    <validator name="bbos-glabel-auditor" status="pass"/>
    <validator name="bbos-truth-gate-validator" status="pass"/>
    <validator name="bbos-stage-completeness-checker" status="fail"/>
  </validators>
  <consolidated_findings>
    <finding validator="bbos-stage-completeness-checker">
      <location>Asset 6 — Risk Reversal / Guarantee</location>
      <issue>missing_deliverable — Operator-Side Boundaries element absent from Guarantee structure</issue>
      <required_fix>Add explicit Operator-Side Boundaries clause specifying what voids the guarantee trigger condition</required_fix>
    </finding>
  </consolidated_findings>
  <governor_recommendation_basis>patch</governor_recommendation_basis>
</bbos_validator_batch_output>
```

---

*This schema is referenced by `docs/governor_stage_handoff_contract.md` and must be used in all multi-validator executions. Single-validator executions may omit the batch wrapper and return the individual `<bbos_validator_output>` directly.*
