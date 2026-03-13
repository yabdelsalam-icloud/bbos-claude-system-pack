# BBOS Operator Session Re-Entry Protocol
@@DOC:BBOS_SESSION_REENTRY@@

**Purpose:** Claude has no memory between conversations. This protocol specifies exactly what the operator must provide at the start of every new session to restore full working context without loss, ambiguity, or stage drift.

---

## Why this protocol exists

Each new Claude conversation begins without any knowledge of previous sessions. If the operator does not re-establish context explicitly, Claude will default to INTAKE MODE — which is the correct fallback behavior, but will cause unnecessary friction if the project is already mid-stage. This protocol makes re-entry deliberate, fast, and reliable.

---

## The re-entry package

At the start of any continuation session, the operator pastes or attaches the following three items **in order**. Nothing else is needed. Nothing should be omitted.

---

### Item 1 — Project state object (required)

Paste the current contents of `state.json` for the project. This is the single source of truth for where the project is and what the last decision was.

**Template reminder:**
```json
{
  "project_id": "...",
  "active_stage": "...",
  "active_command": "...",
  "routing_status": "remain | advance | patch | no_ship",
  "last_validated_at": "YYYY-MM-DD",
  "required_inputs": [],
  "required_validators": [],
  "blocking_issues": [],
  "artifacts": {},
  "notes": []
}
```

**What Claude does with it:** reads `active_stage` and `routing_status` to determine where the session begins, checks `blocking_issues` before accepting any command, and loads the appropriate stage skill.

---

### Item 2 — Active stage asset pack (required if past Stage 00)

Paste or attach the most recent version of the asset pack for the **current active stage**. This is what Claude will work on, patch, assemble, or validate in this session.

If the asset pack is a file, attach it directly. If it is text, paste it after the state object.

**What Claude does with it:** treats this as the working asset. PATCH commands modify this. ASSEMBLE commands extend or complete it. Validators run against it.

---

### Item 3 — Upstream stage asset pack (required for stages 02 and above)

Paste or attach the approved asset pack for the immediately preceding stage. Claude needs this to verify that the active stage's work remains grounded in what was approved upstream.

| Active stage | Upstream pack to include |
|---|---|
| 01 QAL | Stage 00 Normalised Intake Packet |
| 02 STR | Stage 01 QAL Asset Pack |
| 03 OFR | Stage 02 STR Asset Pack |
| 04 OUT | Stage 03 OFR Asset Pack |
| 05 SAL | Stage 04 OUT Asset Pack (and OFR Asset Pack for offer grounding) |
| 06 FUL | Stage 05 SAL Asset Pack + signed client agreement |
| 07 RET | Stage 06 FUL Asset Pack |
| 08 OPT | All active stage packs + Version Log |

---

## Opening message format

After pasting the three items, send the command you want Claude to execute. Use the exact command syntax from the Command Map.

**Example opening message:**
```
[state.json contents pasted here]

[Stage 03 OFR Asset Pack v0.2 pasted here]

[Stage 02 STR Asset Pack pasted here]

PATCH Asset 6 — Guarantee. The Remedy field currently reads "full refund." 
Update to: "refund of the monthly retainer for the month in which the 
trigger condition occurred, applied as a credit toward the next cycle."
```

**Claude's response** will begin by confirming the active stage, the command understood, and the routing status from state — before executing any work.

---

## What happens if items are missing

| Missing item | Claude's behavior |
|---|---|
| No state.json | Claude enters INTAKE MODE and requests intake data |
| State present but no asset pack | Claude issues no_ship and lists what is needed before proceeding |
| Active stage is unclear from state | Claude asks for explicit stage confirmation before loading any skill |
| Upstream pack missing (stages 02+) | Claude flags the gap but may proceed for PATCH commands on isolated sections; will not issue ADVANCE recommendation without it |

---

## Updating state after a session

At the end of every session where meaningful work was done, the operator updates `state.json` manually before closing. Specifically:

- Update `active_command` to the last command executed
- Update `routing_status` to the governor's final recommendation
- Update `blocking_issues` — remove resolved issues, add new ones
- Update `artifacts` with the current file path/version of any updated asset pack
- Add a `notes` entry with timestamp, describing what changed

**Notes entry format:**
```json
{
  "timestamp": "YYYY-MM-DD",
  "author": "operator | system",
  "linked_asset": "asset name or null",
  "note": "Brief description of what changed or was decided"
}
```

---

## Quick-start checklist (print or bookmark this)

Before each session:
- [ ] Open `state.json` — confirm `active_stage` and `routing_status`
- [ ] Have the current stage asset pack ready to paste or attach
- [ ] Have the upstream stage asset pack ready if you are on stage 02 or above
- [ ] Know the command you are going to run (INTAKE / S-OUTPUTS / ASSEMBLE / PATCH / ANNOTATE / RESET ROUTING)

Opening message:
- [ ] Paste state.json
- [ ] Paste or attach active asset pack
- [ ] Paste or attach upstream pack (if applicable)
- [ ] State your command

After each session:
- [ ] Update `state.json` with the governor's final recommendation
- [ ] Save the updated asset pack with a new version number
- [ ] Add a notes entry with today's date

---

*This protocol is the operator's responsibility. Claude cannot persist state between sessions — only the operator can ensure continuity.*
