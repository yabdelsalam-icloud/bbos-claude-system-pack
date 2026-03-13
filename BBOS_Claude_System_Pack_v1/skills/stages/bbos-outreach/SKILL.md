---
name: bbos-outreach
description: Create or revise the Stage 04 OUT Outreach Asset Pack only, using BBOS OUT canon, factories, and assemble contract.
---

# BBOS Stage Skill — OUT

## Purpose
Create or revise the Stage 04 Outreach Asset Pack only.

## Stage identity
Stage: 04_OUT
Allowed anchors:
- @@BBOS_STAGE:OUT@@
- @@SECTION:CANON@@
- @@SECTION:RESEARCH_FACTORY@@
- @@SECTION:ASSET_FACTORY@@
- @@SECTION:ASSEMBLE_CONTRACT@@
- @@SECTION:SPIRITUAL_ANCHOR@@ only when ANNOTATE is explicitly invoked

## You must
- Build the outreach system in canon order.
- Keep hooks as attention devices, not claims.
- Keep scarcity and urgency tied only to real, documented, non-manufactured constraints.
- Keep no-fit language dignified and final.
- Restrict all result language to what is grounded by the OFR Asset Pack.
- Keep a singular, unambiguous CTA per communication where applicable.

## You must not
- Alter the core offer.
- Introduce services not documented in the Scope Map.
- Manufacture urgency.
- Turn opening lines into promises or implied guarantees.
- Use multiple competing CTAs in one communication.

## Required inputs
- approved OFR Asset Pack
- STR VoC and message signal research
- channel landscape
- objection intelligence
- operator outreach constraints
- any current outreach drafts

## Required outputs
1. Channel Plan & Lead Criteria
2. Hook Library
3. Message Library
4. Follow-Up Sequence
5. Appointment Setter & No-Fit Scripts
6. Objection Prep
7. Content-to-DM Pipeline Map

## Completion criteria
- all claims are grounded in approved offer and proof
- hooks do not make claims
- scarcity is documented or absent
- CTA is singular and clear
- no-fit script preserves dignity
- no scope expansion occurs

## NO_SHIP conditions
Return no_ship if:
- no approved OFR Asset Pack exists
- scarcity language is requested without documented constraint
- client-facing claims exceed proof or scope
- the request requires guessing about channel, audience, or scope

## Required output schema
Return exactly:

<bbos_stage_output>
  <stage>04_OUT</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="claims_grounded_in_ofr">met|not_met</criterion>
    <criterion name="hooks_not_claims">met|not_met</criterion>
    <criterion name="scarcity_documented_or_absent">met|not_met</criterion>
    <criterion name="single_clear_cta">met|not_met</criterion>
    <criterion name="no_fit_dignity_preserved">met|not_met</criterion>
    <criterion name="no_scope_expansion">met|not_met</criterion>
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
