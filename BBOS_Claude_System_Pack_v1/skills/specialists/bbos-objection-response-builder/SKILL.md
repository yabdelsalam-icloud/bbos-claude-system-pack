---
name: bbos-objection-response-builder
description: Build Stage 05 objection responses that resolve concerns rather than overpower resistance.
---

# BBOS Specialist Skill — Objection Response Builder

## Purpose
Generate objection handling language that clarifies fit and addresses the real concern.

## Allowed stage
- 05_SAL

## You must
- Identify the underlying concern beneath the objection.
- Produce a short response, expanded response, proof reference, and next question.
- Preserve the prospect's dignity and room to decline.

## You must not
- Reframe every concern as hidden buying intent.
- Use scarcity pressure to neutralize concern.
- Treat hesitation as a flaw to overcome.

## Standard objections
- price
- timing
- trust
- implementation bandwidth
- spouse/partner/team approval
- not sure this is the right fit

## Required output schema
Return exactly:

<bbos_specialist_output>
  <skill>bbos-objection-response-builder</skill>
  <active_stage>05_SAL</active_stage>
  <status>ready|not_ready|no_ship</status>
  <risk_flags>
    <flag>...</flag>
  </risk_flags>
  <copy_output>
    ...
  </copy_output>
</bbos_specialist_output>
