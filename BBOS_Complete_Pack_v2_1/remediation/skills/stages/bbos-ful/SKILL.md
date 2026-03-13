---
name: bbos-ful
description: Execute Stage 06 FUL (Fulfillment). Produces the five Research Factory outputs (FUL_S1–S5) and the complete Fulfillment Asset Pack including Onboarding Checklist, Offboarding Sequence, and delivery architecture. Runs only after a signed client agreement is confirmed.
version: 1.0
---

# BBOS Stage Skill — FUL

## Purpose
Build the delivery architecture that transforms a signed client into a successfully served one. Fulfillment is where every promise made in the offer is either kept or broken. The FUL stage defines how the work gets done, how quality is protected, how the client experiences each milestone, how proof is captured, and how the relationship is handed off to retention.

The governing orientation of this stage is Ihsan — excellence beyond obligation — and Al-Wakil: trustworthy stewardship of what has been entrusted.

---

## Stage identity

Stage: `06_FUL`

Allowed anchors:
- `@@BBOS_STAGE:FUL@@`
- `@@SECTION:CANON@@`
- `@@SECTION:RESEARCH_FACTORY@@`
- `@@SECTION:ASSET_FACTORY@@`
- `@@SECTION:ASSEMBLE_CONTRACT@@`
- `@@SECTION:SPIRITUAL_ANCHOR@@` — only when ANNOTATE is explicitly invoked

---

## Canon principles (non-negotiable)

**The offer governs delivery scope.** Every fulfillment deliverable traces to a specific item in the OFR Asset Pack Scope Map. Nothing outside the scope map is delivered. Nothing inside the scope map is silently omitted.

**The scope map exclusions are enforced, not softened.** The Excluded column of the Scope Map exists precisely for the moments when a client asks for something outside scope. The FUL stage does not renegotiate scope — it executes it.

**Proof is captured, not assumed.** Every client success moment is an opportunity to capture proof for Stage 07 RET and future offers. FUL_S4 exists to plan this capture in advance — not as an afterthought.

**The offboarding handoff seeds retention.** The end of fulfillment is not a goodbye — it is the first act of Stage 07. The offboarding sequence is designed to close well and open the next conversation.

**No scope expansion under delivery pressure.** If the client requests work outside the scope map, the operator names the boundary clearly and documents the request. Scope creep is not generosity — it is a failure of stewardship toward the operator's own capacity and toward the promise made to subsequent clients.

---

## Required inputs

- Approved OFR Asset Pack (Scope Map, Promise, Guarantee, Pricing — all confirmed)
- Signed client agreement (confirms the specific scope variant agreed)
- SAL Asset Pack (client qualification data, onboarding trigger notes)
- STR Asset Pack (for FUL_S3 client success language continuity)

If any required input is missing: return NO_SHIP with the specific item, why it is required, and what would resolve the gap.

---

## Research Factory: FUL_S1–S5

| Output | Description |
|---|---|
| FUL_S1 — Offer-to-Delivery Map | Phase-by-phase breakdown of how the offer is delivered. Each phase includes: deliverables, checkpoints, owner (operator/client), timeline, and dependency on prior phase. Every item maps to a named scope item from the OFR Scope Map. |
| FUL_S2 — Quality & Risk Map | The top failure modes for this specific offer type, the quality control check for each one, the guarantee trigger conditions that apply (from OFR Asset 6), and the operator-side mitigation for each risk. This is a protection document, not a liability list. |
| FUL_S3 — Client Success Milestones | 3–5 checkpoints across the delivery cycle where the client can observe progress. For each: what the client will see/feel/receive, the message or communication sent at that milestone, and how the milestone connects to the original promise. Language carries forward from STR buying language where relevant. |
| FUL_S4 — Proof Capture Plan | What proof to capture, at which milestone, in what format, with what consent protocol. Covers: client results documentation, testimonial or case study trigger, before/after evidence, and handoff to RET proof asset deployment. |
| FUL_S5 — Offboarding → Retention Handoff Notes | Close sequence: what the operator says, sends, and documents at the end of the engagement. Includes the retention seed (the first touch in Stage 07), next logical offer (for RET upsell path), and any unresolved proof capture items. |

**Hard rules for Research Factory:**
- Do not invent scope, timeline, or deliverables not present in the OFR Asset Pack.
- FUL_S2 failure modes must map to real risks for this specific offer — not generic consulting risks.
- FUL_S3 milestone language must be consistent with OFR Promise language — do not introduce new commitments.

---

## Asset Factory: Fulfillment Asset Pack

| Asset | Description |
|---|---|
| Onboarding Checklist | Payment-to-work-start steps with owner (operator/client), timing, and completion trigger. Includes the IC-FUL Onboarding Communication Checklist: does every onboarding communication give the client an unbroken understanding of what they will receive, when, and from whom? |
| Quality Control Checklist | Per-phase quality gates drawn from FUL_S2. Each gate: what is checked, what pass looks like, what fail triggers, and who owns the resolution. The Al-Wali standard applies: this document is about protection, not compliance. |
| Client Success Milestones (Asset Pack version) | The client-facing version of FUL_S3 — what the client receives at each milestone point, formatted for operator use in the delivery cycle. |
| Scope Enforcement Protocol | The specific language the operator uses when a client requests work outside the scope map. Firm, clear, and dignified. Documents where to log out-of-scope requests and how to route them (decline, quote, or defer to next engagement). |
| Offboarding Sequence | The structured close: final delivery confirmation, results summary, proof capture request, retention seed message, and documented handoff to Stage 07 RET. |

---

## Completion criteria

- FUL_S1 maps every delivery phase to a named OFR scope item
- FUL_S2 identifies real failure modes for this offer type, not generic risks
- FUL_S3 milestone language is consistent with OFR Promise — no new commitments
- FUL_S4 proof capture plan has specific triggers and consent protocol
- FUL_S5 offboarding includes retention seed and next-offer identification
- Onboarding Checklist covers payment-to-work-start without gaps
- Scope Enforcement Protocol is specific enough to use in a live conversation
- Offboarding Sequence includes the RET handoff trigger

---

## NO_SHIP conditions

Return `no_ship` if:
- Approved OFR Asset Pack is absent
- Signed client agreement is absent — scope cannot be confirmed without it
- FUL_S1 would require inventing scope not present in the OFR Scope Map
- FUL_S3 would require making promises not in the approved OFR Asset Pack
- The request requires crossing into Stage 07 RET work

---

## Spiritual annotation placement (when ANNOTATE is explicitly invoked)

Governing attributes: **Al-Muhsin · Al-Wali · Ash-Shakur**

- Before FUL_S2 (Quality & Risk Map): ⧁ Al-Wali — the operator is the protective friend of what has been entrusted to them. This quality control document is an act of guardianship, not bureaucracy.
- Before FUL_S3 (Client Success Milestones): ⧁ Al-Muhsin — Al-Muhsin does not simply fulfill obligation. He perfects it. The milestones are the moments where the gap between adequate and excellent opens. Design for the excellent.
- Before FUL_S5 (Offboarding → Retention Handoff): ⧁ Ash-Shakur — the offboarding is an act of gratitude for the trust placed. The retention seed that flows from genuine appreciation carries something that no sequence built from extraction can manufacture.
- Before Quality Control Checklist in Asset Factory: ⧁ Al-Wali — protection, not process.
- Before Client Success Milestones in Asset Factory: ⧁ Al-Muhsin — design for excellence, not adequacy.

All annotations: 2 sentences maximum. One specific operational implication. Use only Al-Muhsin, Al-Wali, or Ash-Shakur — do not import attributes from other stages.

---

## Required output schema

```xml
<bbos_stage_output>
  <stage>06_FUL</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="ful_s1_maps_to_ofr_scope">met|not_met</criterion>
    <criterion name="ful_s2_real_failure_modes">met|not_met</criterion>
    <criterion name="ful_s3_consistent_with_ofr_promise">met|not_met</criterion>
    <criterion name="ful_s4_proof_capture_with_consent">met|not_met</criterion>
    <criterion name="ful_s5_offboarding_seeds_retention">met|not_met</criterion>
    <criterion name="onboarding_checklist_complete">met|not_met</criterion>
    <criterion name="scope_enforcement_protocol_present">met|not_met</criterion>
  </criteria_report>
  <missing_inputs>
    <item>...</item>
  </missing_inputs>
  <blocking_issues>
    <issue>...</issue>
  </blocking_issues>
  <updated_asset>
    <!-- Complete FUL Asset Pack in order:
         FUL_S1–S5 → Onboarding Checklist → QC Checklist →
         Client Success Milestones → Scope Enforcement Protocol →
         Offboarding Sequence -->
    ...
  </updated_asset>
</bbos_stage_output>
```
