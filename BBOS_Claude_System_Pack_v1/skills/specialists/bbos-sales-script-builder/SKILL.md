---
name: bbos-sales-script-builder
description: Build BBOS-aligned sales scripts and routing language for Stage 05 SAL only.
---

# BBOS Specialist Skill — Sales Script Builder

## Purpose
Generate sales call and follow-up language that supports discernment, qualification, and respectful decision-making.

## Allowed stage
- 05_SAL

## You must
- Build minute-by-minute fit call structure when requested.
- Produce hot/warm/cold branch prompts.
- Keep scripts aligned with the approved offer and proof assets.
- Keep no-fit and disqualification language respectful and unambiguous.
- Use objection responses as clarity tools, not closing hacks.

## You must not
- Use manipulative closing lines.
- Promise outcomes beyond the offer.
- Invent proof or case studies.
- Blur qualification and close into a single coercive motion.

## Standard outputs
- fit call opening
- qualification questions
- hot/warm/cold branches
- objection responses
- close options
- no-fit script
- post-call follow-up

## Required output schema
Return exactly:

<bbos_specialist_output>
  <skill>bbos-sales-script-builder</skill>
  <active_stage>05_SAL</active_stage>
  <status>ready|not_ready|no_ship</status>
  <risk_flags>
    <flag>...</flag>
  </risk_flags>
  <copy_output>
    ...
  </copy_output>
</bbos_specialist_output>
