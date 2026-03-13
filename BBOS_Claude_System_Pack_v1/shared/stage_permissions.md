# BBOS Stage Permissions
@@DOC:BBOS_STAGE_PERMISSIONS@@

**This file is the authoritative source for which specialist and validator skills are permitted at each stage. The governor loads skills from this file — it does not load from individual skill files' `allowed_stages` declarations. Any conflict between this file and an individual skill's `allowed_stages` field must be resolved by updating the skill file to match this document.**

---

## Specialist skills by stage

| Stage | Permitted specialists |
|---|---|
| 00 INT / 00.1 IFB | — (no specialists; intake is capture and normalisation only) |
| 01 QAL / 01.1 REJ | — (no specialists; QAL is assessment and screening only) |
| 02 STR / 02.1 STRESS | `bbos-copywriting-architect` · `bbos-content-idea-engine` |
| 03 OFR | `bbos-copywriting-architect` |
| 04 OUT | `bbos-copywriting-architect` · `bbos-content-idea-engine` · `bbos-hook-library-builder` · `bbos-objection-response-builder` |
| 05 SAL / 05.1 DQ | `bbos-copywriting-architect` · `bbos-sales-script-builder` · `bbos-objection-response-builder` |
| 06 FUL | — (fulfillment is delivery architecture; no copy specialists) |
| 07 RET | `bbos-copywriting-architect` · `bbos-content-idea-engine` |
| 08 OPT | — (optimization is review and iteration; no copy specialists) |

> **Note on `bbos-objection-response-builder`:** This skill is permitted at both `04 OUT` and `05 SAL`. The skill's own `allowed_stage` field previously declared SAL only — this was an error in the skill file. The skill file has been updated to match this permissions table (see `specialists/bbos-objection-response-builder/SKILL.md` remediation). At OUT, the skill produces outreach-context objection preparation. At SAL, it produces fit-call objection responses. The outputs differ but the skill governs both.

---

## Validator skills by stage

| Stage | Required validators (must all pass before ADVANCE) | Optional validators |
|---|---|---|
| 00 INT | — | — |
| 00.1 IFB | — | — |
| 01 QAL | — | — |
| 01.1 REJ | — | — |
| 02 STR | — | `bbos-truth-gate-validator` |
| 02.1 STRESS | — | — |
| 03 OFR | `bbos-glabel-auditor` · `bbos-truth-gate-validator` · `bbos-stage-completeness-checker` | — |
| 04 OUT | `bbos-truth-gate-validator` · `bbos-scarcity-checker` · `bbos-stage-completeness-checker` | `bbos-glabel-auditor` |
| 05 SAL | `bbos-truth-gate-validator` · `bbos-scarcity-checker` · `bbos-stage-completeness-checker` | — |
| 05.1 DQ | — | — |
| 06 FUL | `bbos-stage-completeness-checker` | `bbos-truth-gate-validator` |
| 07 RET | `bbos-truth-gate-validator` · `bbos-stage-completeness-checker` | — |
| 08 OPT | `bbos-stage-completeness-checker` | — |

> **Note on `bbos-scarcity-checker` at SAL:** The SAL stage produces reminders, follow-up sequences, and time-limited close language. All of this is subject to manufactured urgency risk. `bbos-scarcity-checker` is now required at SAL, not optional. This closes the coverage gap identified in the pre-launch audit.

---

## Governor loading rule

When the governor resolves the active stage, it loads:
1. The active stage skill from `stages/` matching the active_stage code.
2. All permitted specialists from this file for that stage — **only those explicitly requested by the operator or required by the active command**.
3. All required validators from this file for that stage — **these are loaded before any ADVANCE recommendation is issued**.

The governor never loads a specialist or validator not listed in this table for the active stage, regardless of what the skill file itself claims.

---

*Last updated: remediation pass v1.0 — objection-response-builder OUT permission restored; scarcity-checker added as required validator at SAL.*
