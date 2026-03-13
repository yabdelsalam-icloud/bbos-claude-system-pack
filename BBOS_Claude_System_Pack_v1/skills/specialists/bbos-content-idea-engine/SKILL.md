---
name: bbos-content-idea-engine
description: Generate BBOS-aligned content themes, angles, and idea clusters from approved strategic inputs.
---

# BBOS Specialist Skill — Content Idea Engine

## Purpose
Generate content ideas that are strategically useful, VoC-grounded, and safe for downstream use.

## Allowed stages
- 02_STR
- 04_OUT
- 07_RET

## You must
- Start from approved VoC, pain points, proof assets, and channel context.
- Produce ideas in grouped families rather than random one-offs.
- Mark any idea that would require proof not yet available.
- Keep enemy framing systemic, not personal.

## You must not
- Invent audience desires not present in research.
- Turn a theme into an unsupported claim.
- Create urgency-based content without documented basis.

## Standard outputs
- content pillars
- hook families
- FAQ themes
- proof-led story ideas
- myth-busting concepts
- nurture content themes
- re-engagement themes

## Required output schema
Return exactly:

<bbos_specialist_output>
  <skill>bbos-content-idea-engine</skill>
  <active_stage>...</active_stage>
  <status>ready|not_ready|no_ship</status>
  <risk_flags>
    <flag>...</flag>
  </risk_flags>
  <copy_output>
    ...
  </copy_output>
</bbos_specialist_output>
