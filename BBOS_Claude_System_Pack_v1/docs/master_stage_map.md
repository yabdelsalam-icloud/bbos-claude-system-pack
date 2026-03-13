# BBOS Master Stage Map v4
@@DOC:BBOS_MASTER_STAGE_MAP@@

**Source authority: Priority 1 — all modules defer to this document in any conflict.**

---

## Complete Stage Registry

| Code | Stage | Sub-stage of | Description |
|------|-------|-------------|-------------|
| 00 | INT — Intake | — | Operator self-assessment and foundational capability audit. All six intake sections completed. No strategic work begins before routing decision is issued. |
| 00.1 | IFB — Intake Form Build | 00 | Design, test, and deploy the Google Form intake instrument. Produces the intake instrument itself, not intake data. |
| 01 | QAL — Qualification & Alignment | — | Six-pillar strategic mandate. Viability pre-check. Amanah screening rubric. No offer work begins before QAL asset pack is approved. |
| 01.1 | REJ — Rejection | 01 | Issued when automatic disqualifiers are triggered during QAL intake screening. Routing to REJ is an act of stewardship, not failure. Produces dignified rejection with specific basis. |
| 02 | STR — Strategy | — | Synthesizes QAL asset pack into the strategic foundation: belief, positioning, mechanism, market narrative. |
| 02.1 | STRESS — Strategy Stress Test | 02 | Adversarial stress test of STR outputs before OFR begins. Surfacing structural weaknesses before commercial commitments are made. |
| 03 | OFR — Offer | — | Constructs the complete offer asset pack: promise, ICP, mechanism, scope map, value stack, guarantee, pricing, proof plan. |
| 04 | OUT — Outreach | — | Builds the outreach system: channel plan, hook library, message library, follow-up sequence, appointment setter, no-fit scripts, content-to-DM pipeline. |
| 05 | SAL — Sales | — | Builds the sales system: qualification form, DM automation spec, decision tree, fit call script, objection library, nurture and reminders. |
| 05.1 | DQ — Disqualification | 05 | Issued when a prospect fails qualification during the sales stage. Produces respectful, unambiguous no-fit handling. |
| 06 | FUL — Fulfillment | — | Delivery architecture: client onboarding, delivery playbook, scope enforcement, communication cadence, results documentation. |
| 07 | RET — Retention | — | Post-delivery relationship: re-engagement sequences, upsell paths, proof asset deployment, referral activation. |
| 08 | OPT — Optimization | — | Structured review and iteration cycle: hold list, test candidates, version log, learning capture. |

---

## Linear Progression and Gate Rules

Each stage gates the one above it. No stage may begin unless its prerequisite stage has reached `routing_status: advance`.

```
00 INT → 01 QAL → 02 STR → 03 OFR → 04 OUT → 05 SAL → 06 FUL → 07 RET → 08 OPT
```

Sub-stages are lateral, not forward:
- `00.1 IFB` runs in parallel with or immediately after `00 INT` — produces the intake instrument.
- `01.1 REJ` exits the forward progression — operator does not advance until REJ basis is resolved or operator restarts.
- `02.1 STRESS` must pass before `03 OFR` begins.
- `05.1 DQ` is a terminal exit for that prospect — the pipeline continues with other candidates.

---

## Stage Transition Prerequisites

| Transition | Required condition before advancing |
|---|---|
| 00 → 01 | All six intake sections complete. No automatic disqualifiers present. Routing Decision issued as `proceed`. |
| 01 → 02 | QAL Asset Pack approved (S1–S6 complete, V1–V3 complete, Asset Factory outputs complete, Amanah Gate passed). |
| 02 → 03 | STR Asset Pack approved. `02.1 STRESS` test passed or formally waived with documented reason. |
| 03 → 04 | OFR Asset Pack approved. All required validators passed: glabel-auditor, truth-gate, stage-completeness. |
| 04 → 05 | OUT Asset Pack approved. All required validators passed: truth-gate, scarcity-checker, stage-completeness. |
| 05 → 06 | SAL Asset Pack approved. Client signed. Onboarding trigger confirmed. |
| 06 → 07 | Delivery cycle complete. Results documented. Client formally transitioned out of active fulfillment. |
| 07 → 08 | Retention cycle complete (minimum one review period elapsed). |

---

## Spiritual Architecture by Stage

| Stage | Governing Attributes | Core Orientation |
|---|---|---|
| 00 INT | Al-Awwal · Ash-Shahid | Honest declaration before God before anything is built |
| 01 QAL | Al-Haqq · Al-Khabir | Truth as foundation; God knows the hidden realities |
| 02 STR | Al-Basir · Al-Hakim | Clear sight and wisdom in how the foundation is structured |
| 03 OFR | Al-Adl · As-Sami | Justice in what is promised; God hears every commitment |
| 04 OUT | Al-Latif · Al-Wadud | Gentleness and love as the posture of invitation |
| 05 SAL | Ar-Razzaq · Al-Latif · As-Sittir | Discernment over closing; presence over pressure |
| 06 FUL | Al-Wakil · Al-Muqit | Trustworthy stewardship; nourishing what has been entrusted |
| 07 RET | Al-Wadud · Al-Karim | Loving generosity in the ongoing relationship |
| 08 OPT | Al-Khabir · Al-Hakim | Knowing what actually happened; wisdom in what to change |

Spiritual annotations are operator-facing only. They are never auto-generated. ANNOTATE must be explicitly invoked. See `shared/spiritual_layer_rules.md` for full constraints.

---

## Allowed Anchors by Stage

| Stage | Stage anchor | Allowed section anchors |
|---|---|---|
| 00 INT | `@@BBOS_STAGE:INT@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 00.1 IFB | `@@BBOS_STAGE:IFB@@` | CANON · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 01 QAL | `@@BBOS_STAGE:QAL@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 01.1 REJ | `@@BBOS_STAGE:REJ@@` | CANON · ASSEMBLE_CONTRACT |
| 02 STR | `@@BBOS_STAGE:STR@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 02.1 STRESS | `@@BBOS_STAGE:STRESS@@` | CANON · ASSEMBLE_CONTRACT |
| 03 OFR | `@@BBOS_STAGE:OFR@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 04 OUT | `@@BBOS_STAGE:OUT@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 05 SAL | `@@BBOS_STAGE:SAL@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 05.1 DQ | `@@BBOS_STAGE:DQ@@` | CANON · ASSEMBLE_CONTRACT |
| 06 FUL | `@@BBOS_STAGE:FUL@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 07 RET | `@@BBOS_STAGE:RET@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT · SPIRITUAL_ANCHOR (explicit only) |
| 08 OPT | `@@BBOS_STAGE:OPT@@` | CANON · RESEARCH_FACTORY · ASSET_FACTORY · ASSEMBLE_CONTRACT |

---

## Stage Skill File Registry

| Stage | Skill file | Status |
|---|---|---|
| 00 INT / 00.1 IFB | `stages/bbos-intake/SKILL.md` | ✅ Authored v1.0 |
| 01 QAL / 01.1 REJ | `stages/bbos-qal/SKILL.md` | ⚠️ Pending authorship |
| 02 STR / 02.1 STRESS | `stages/bbos-str/SKILL.md` | ⚠️ Pending authorship |
| 03 OFR | `stages/bbos-offer/SKILL.md` | ✅ Complete |
| 04 OUT | `stages/bbos-outreach/SKILL.md` | ✅ Complete |
| 05 SAL / 05.1 DQ | `stages/bbos-sales/SKILL.md` | ✅ Complete |
| 06 FUL | `stages/bbos-ful/SKILL.md` | ⚠️ Pending authorship |
| 07 RET | `stages/bbos-ret/SKILL.md` | ⚠️ Pending authorship |
| 08 OPT | `stages/bbos-opt/SKILL.md` | ⚠️ Pending authorship |

---

*Version: 4.0 | Governing document for all BBOS runtime modules. Do not modify stage codes, prerequisite rules, or anchor names without updating all dependent skill files.*
