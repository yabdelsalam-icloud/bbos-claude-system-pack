---
name: bbos-ret
description: Execute Stage 07 RET (Retention). Produces the five Research Factory outputs (S1–S5) and the six canon deliverables of the Retention Asset Pack. Governs re-engagement, upsell paths, and proof asset deployment — from a place of genuine relationship, not extraction.
version: 1.0
---

# BBOS Stage Skill — RET

## Purpose
Sustain and deepen the relationship with past clients: re-engage those who have gone quiet, offer natural next steps to those ready for more, and deploy proof assets that serve both the client's story and the operator's future offers. The governing quality of this stage is Al-Wadud — love that is tender, consistent, and entirely free of transaction.

This stage is not a re-acquisition funnel dressed in polite language. Every sequence, every upsell framing, every proof request must be built from genuine appreciation for the relationship, or it will not carry what it is meant to carry.

---

## Stage identity

Stage: `07_RET`

Allowed anchors:
- `@@BBOS_STAGE:RET@@`
- `@@SECTION:CANON@@`
- `@@SECTION:RESEARCH_FACTORY@@`
- `@@SECTION:ASSET_FACTORY@@`
- `@@SECTION:ASSEMBLE_CONTRACT@@`
- `@@SECTION:SPIRITUAL_ANCHOR@@` — only when ANNOTATE is explicitly invoked

---

## Canon principles (non-negotiable)

**Re-engagement is warming, not pushing.** The Cold Lead Re-Engagement Sequence has five touches. Each one offers value or acknowledgment first. No touch is a naked ask. No touch manufactures urgency. A person who does not respond after five touches is not pushed further.

**The upsell path is a natural continuation, not an extraction.** The next offer is framed as the logical next step in the client's own journey — not as a revenue event for the operator. If the client is not ready, the relationship is preserved. A no-fit path must exist in the upsell framing.

**Proof belongs to the client first.** Proof assets are the client's story. Their permission governs how and where it is used. The Proof Asset Deployment Map includes the consent protocol for every asset type. Proof is never deployed without the client's explicit agreement.

**Canonical Metrics track what actually matters.** The four CM metrics (CM-1 through CM-4) measure real relationship health — fulfillment quality, re-engagement response, referral rate, and lifetime value. They are not vanity metrics. If they are unflattering, they are reported accurately.

---

## Required inputs

- FUL Asset Pack (Offboarding Sequence, FUL_S5 RET handoff notes, proof capture plan)
- OFR Asset Pack (for upsell path next-offer framing)
- STR Asset Pack (for re-engagement message language continuity)
- Client segmentation data: who has completed, who is dormant, who is a warm referral candidate

If any required input is missing: return NO_SHIP with the specific item and resolution path.

---

## Research Factory: S1–S5

| Output | Description |
|---|---|
| S1 — Segment Map | Classify all past clients and prospects into segments: active (current clients), completed (delivered and offboarded), dormant (60+ days silent post-delivery), cold leads (never converted), referral candidates (high satisfaction, natural advocates). Each segment has its own sequence path. |
| S2 — Proof Inventory | Catalogue all proof assets available from Stage 06: testimonials, case studies, before/after documentation, results screenshots, client statements. Note consent status for each. Flag any proof capture items from FUL_S4 not yet completed. |
| S3 — Offer Continuation Map | Define the natural next offer for each segment. Frame each as a continuation of what the client has already experienced — not a new sale. Include the no-fit path for clients who are not ready or not a fit for the next offer. |
| S4 — Message Spine and Tone Rules | The governing tone principles for all RET communications: what language carries Al-Wadud, what language signals extraction, what openings feel like genuine reaching-out vs. pipeline management. Three to five specific examples of each. |
| S5 — Deployment Logic | Which proof assets go to which channels at which stage of the retention sequence. Maps: Segment → Sequence → Touch number → Asset type → Consent requirement. |

---

## Asset Factory: Six Canon Deliverables

All six deliverables must be present before `<decision>ready</decision>` is returned.

| # | Deliverable | Specification |
|---|---|---|
| 1 | Cold Lead Re-Engagement Sequence | Five-touch sequence for dormant contacts who never converted. Each touch: subject/opening line, core message (value or acknowledgment first), CTA (soft, specific, non-pressuring). No manufactured urgency. Touch 5 is a dignified close — if no response, the sequence ends. |
| 2 | Past Client Check-In Sequence | Three-touch sequence for completed clients (post-delivery). Touch 1: genuine check-in, no ask. Touch 2: value delivery (insight, resource, relevant observation). Touch 3: natural next step offer with clear no-fit path. |
| 3 | Referral Activation Sequence | For high-satisfaction completed clients. Frames the referral ask as an act of generosity toward someone the client cares about — not a commission opportunity. Includes what to say, what to offer (if anything), and how to receive a referral with care. |
| 4 | Upsell Path and Ascension Framework | The next offer framed as natural continuation. Includes: what the client has already experienced (anchor), what the next step addresses (continuation), what changes if they do nothing (gentle consequence, not fear), and the no-fit path. G4-labeled for all outcome language. |
| 5 | Canonical Metrics Dashboard | Current values for CM-1 (Fulfillment Quality Score), CM-2 (Re-Engagement Response Rate), CM-3 (Referral Rate), CM-4 (Client Lifetime Value trend). Reported accurately — unflattering numbers are not softened. |
| 6 | Proof Asset Deployment Map | Table: Segment → Sequence → Touch number → Proof asset → Consent status → Deployment channel. Only assets with confirmed client consent are listed for deployment. Pending consent items are flagged separately. |

---

## Completion criteria

- S1 segments are mutually exclusive and cover all past client/lead categories
- S2 proof inventory includes consent status for every asset
- S3 continuation map includes a no-fit path for every next-offer framing
- S4 tone rules distinguish Al-Wadud language from extraction language with examples
- All six canon deliverables present and complete
- Cold lead sequence ends with a dignified close at touch 5 — no indefinite push
- Upsell path includes the no-fit path
- Proof Asset Deployment Map only deploys assets with confirmed consent
- CM-1 through CM-4 are reported accurately

---

## NO_SHIP conditions

Return `no_ship` if:
- FUL Asset Pack is absent — segmentation, proof inventory, and offboarding handoff cannot be built without it
- S2 proof inventory would require deploying proof assets without documented consent
- S3 continuation map would require introducing services not in the approved OFR or a subsequent approved offer
- The upsell framing requires manufactured urgency or scarcity
- The request requires generating outreach or sales assets (Stage 04/05 work)

---

## Spiritual annotation placement (when ANNOTATE is explicitly invoked)

Governing attributes: **Al-Wadud · Ash-Shakur**

- Before S1 Segment Map: ⧁ Ash-Shakur — each segment represents a human being who placed trust in the operator's work. The segment map is not a lead list. It is an accounting of relationships, and the first act of that accounting is gratitude for each one.
- Before S3 Offer Continuation Map: ⧁ Al-Wadud — the next offer is offered from love, not from pipeline pressure. Al-Wadud does not calculate return on investment before reaching out. The sequence built from this quality will carry something no technique can replicate.
- Before Deliverable 1 (Cold Lead Re-Engagement): ⧁ Al-Wadud — the sequence that warms rather than pushes comes from genuine care. A contact who never converted is still a person who considered placing trust. That deserves warmth.
- Before Deliverable 4 (Upsell Path): ⧁ Al-Wadud — the upsell path built from love asks only what serves the client's genuine continuation. Al-Wadud does not love in order to receive something in return.
- Before Deliverable 6 (Proof Asset Deployment Map): ⧁ Ash-Shakur — the client's story belongs to them first. Deploying it is an act of gratitude and stewardship, not a marketing move. Handle it accordingly.

All annotations: 2 sentences maximum. One specific operational implication. Use only Al-Wadud and Ash-Shakur for RET outputs.

---

## Required output schema

```xml
<bbos_stage_output>
  <stage>07_RET</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="segment_map_complete_with_all_categories">met|not_met</criterion>
    <criterion name="proof_inventory_consent_status_documented">met|not_met</criterion>
    <criterion name="continuation_map_includes_no_fit_path">met|not_met</criterion>
    <criterion name="all_six_deliverables_present">met|not_met</criterion>
    <criterion name="cold_lead_sequence_ends_with_dignified_close">met|not_met</criterion>
    <criterion name="proof_deployment_consent_confirmed">met|not_met</criterion>
    <criterion name="cm1_cm4_reported_accurately">met|not_met</criterion>
  </criteria_report>
  <missing_inputs>
    <item>...</item>
  </missing_inputs>
  <blocking_issues>
    <issue>...</issue>
  </blocking_issues>
  <updated_asset>
    <!-- Complete RET Asset Pack in order:
         S1–S5 → Deliverables 1–6 -->
    ...
  </updated_asset>
</bbos_stage_output>
```
