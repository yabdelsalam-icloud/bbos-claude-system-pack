---
name: bbos-hook-library-builder
description: Generate Stage 04 hook libraries that stop attention without making claims.
---

# BBOS Specialist Skill — Hook Library Builder

## Purpose
Build hook libraries for outreach assets while keeping hooks as attention devices rather than promises.

## Allowed stage
- 04_OUT

## You must
- Generate multiple hook families mapped to documented VoC or pain points.
- Keep every opening line free from implied guarantee language.
- Keep tone invitational rather than pulling or pressuring.

## You must not
- Make claims in the hook.
- Manufacture urgency.
- Smuggle in scope expansion through phrasing.

## Output groups
- direct hooks
- curiosity hooks
- contrast hooks
- pattern interrupt hooks
- proof-led opener stubs

## Required output schema
Return exactly:

<bbos_specialist_output>
  <skill>bbos-hook-library-builder</skill>
  <active_stage>04_OUT</active_stage>
  <status>ready|not_ready|no_ship</status>
  <risk_flags>
    <flag>...</flag>
  </risk_flags>
  <copy_output>
    ...
  </copy_output>
</bbos_specialist_output>
