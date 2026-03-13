---
name: bbos-offer
description: Create or revise the Stage 03 OFR Offer Asset Pack only, using BBOS OFR canon, factories, and assemble contract.
---

# BBOS Stage Skill — OFR

## Purpose
Create or revise the Stage 03 Offer Asset Pack only.

## Stage identity
Stage: 03_OFR
Allowed anchors:
- @@BBOS_STAGE:OFR@@
- @@SECTION:CANON@@
- @@SECTION:RESEARCH_FACTORY@@
- @@SECTION:ASSET_FACTORY@@
- @@SECTION:ASSEMBLE_CONTRACT@@
- @@SECTION:SPIRITUAL_ANCHOR@@ only when ANNOTATE is explicitly invoked

## You must
- Build the Offer Asset Pack in canon order.
- Keep the core Promise limited to G1 or G2 only.
- Keep all result-implying language correctly G-labeled.
- Make Scope Map exclusions explicit.
- Ensure the Guarantee contains all four elements:
  - Trigger Condition
  - Scope
  - Remedy
  - Operator-Side Boundaries
- Ensure Pricing is specific, transparent, and aligned with the Value Stack.
- Flag proof-dependent claims as PROOF PENDING when proof is missing.
- Respect operator constraints from upstream stages.

## You must not
- Perform outreach-stage or sales-stage work.
- Invent proof, testimonials, guarantees, pricing rationale, or scope items.
- Upgrade G3 language to G2 without explicit justification and validator pass.
- Use aspirational G4 language as if it were a commitment.
- Proceed when required inputs are missing.

## Required inputs
- STR Asset Pack or stage-approved strategic inputs
- OFR research inputs S1–S5 where applicable
- operator constraints
- pricing references
- proof references
- any existing draft offer asset pack

## Output order
1. Asset 1 — Promise
2. Asset 2 — Ideal Customer Profile
3. Asset 3 — Mechanism
4. Asset 4 — Scope Map
5. Asset 5 — Value Stack
6. Asset 6 — Risk Reversal / Guarantee
7. Asset 7 — Pricing Structure
8. Asset 8 — Proof Plan

## Completion criteria
- Promise is clearly stated and limited to G1/G2
- G-labels are correct
- Scope exclusions are explicit
- Guarantee has all four required elements
- Pricing and value stack tell the same story
- Proof-dependent claims are anchored or marked PROOF PENDING
- No unsupported certainty theater remains

## NO_SHIP conditions
Return no_ship if:
- required strategic inputs are missing
- proof is required for a client-facing G1/G2 claim and none is provided
- contradictions exist in scope, guarantee, or pricing
- the request requires guessing

## Required output schema
Return exactly:

<bbos_stage_output>
  <stage>03_OFR</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="promise_g1_g2_only">met|not_met</criterion>
    <criterion name="glabels_correct">met|not_met</criterion>
    <criterion name="scope_exclusions_explicit">met|not_met</criterion>
    <criterion name="guarantee_four_elements">met|not_met</criterion>
    <criterion name="pricing_value_stack_alignment">met|not_met</criterion>
    <criterion name="proof_anchors_present_or_pending">met|not_met</criterion>
    <criterion name="no_certainty_theater">met|not_met</criterion>
  </criteria_report>
  <missing_inputs>
    <item>...</item>
  </missing_inputs>
  <blocking_issues>
    <issue>...</issue>
  </blocking_issues>
  <updated_asset>
    ...
  </updated_asset>
</bbos_stage_output>
