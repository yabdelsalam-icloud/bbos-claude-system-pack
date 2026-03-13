---
name: bbos-sales
description: Create or revise the Stage 05 SAL Sales Asset Pack only, using BBOS SAL canon, factories, and assemble contract.
---

# BBOS Stage Skill — SAL

## Purpose
Create or revise the Stage 05 Sales Asset Pack only.

## Stage identity
Stage: 05_SAL
Allowed anchors:
- @@BBOS_STAGE:SAL@@
- @@SECTION:CANON@@
- @@SECTION:RESEARCH_FACTORY@@
- @@SECTION:ASSET_FACTORY@@
- @@SECTION:ASSEMBLE_CONTRACT@@
- @@SECTION:SPIRITUAL_ANCHOR@@ only when ANNOTATE is explicitly invoked

## You must
- Build the sales system in canon order.
- Treat qualification as a real gate, not a revenue inconvenience.
- Build the fit call as a discernment conversation.
- Use objection responses as clarity tools, not pressure tools.
- Preserve dignity in all no-fit paths.
- Keep follow-up and reminders value-led rather than pressure-led.

## You must not
- Rewrite the offer inside the sales stage.
- Use coercive scripts.
- Keep a prospect in ambiguity when the answer is no-fit.
- Ignore disqualifiers because the pipeline is thin.
- Promise outcomes not grounded in approved offer/proof.

## Required outputs
1. Qualification Form
2. DM Automation Flow Spec
3. Decision Tree
4. Fit Call Script
5. Objection Library
6. Nurture + Reminders + Follow-Up

## Completion criteria
- qualification logic is explicit
- hot/warm/cold routing is operational
- fit call reflects discernment rather than pressure
- objections clarify concerns rather than bulldozing them
- no-fit language is clear and respectful
- reminders and follow-up are value-led and specific

## Required output schema
Return exactly:

<bbos_stage_output>
  <stage>05_SAL</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="qualification_logic_explicit">met|not_met</criterion>
    <criterion name="routing_operational">met|not_met</criterion>
    <criterion name="fit_call_discernment">met|not_met</criterion>
    <criterion name="objection_clarity_not_pressure">met|not_met</criterion>
    <criterion name="no_fit_dignity_preserved">met|not_met</criterion>
    <criterion name="follow_up_value_led">met|not_met</criterion>
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
