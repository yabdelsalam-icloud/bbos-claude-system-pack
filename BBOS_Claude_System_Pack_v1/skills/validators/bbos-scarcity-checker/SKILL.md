---
name: bbos-scarcity-checker
description: Verify that all scarcity or urgency language is tied to a real, documented, non-manufactured constraint.
---

# BBOS Validator — Scarcity Checker

## Purpose
Validate all urgency and scarcity language in outreach or sales assets.

## You must
- identify every urgency or scarcity phrase
- require a named documented constraint for each one
- fail any undocumented or theatrical urgency

## You must not
- accept vague references to limited spots, time, or availability without documentation
- treat emotional urgency as operational urgency

## Required output schema
Return exactly:

<bbos_validator_output>
  <validator>bbos-scarcity-checker</validator>
  <status>pass|fail</status>
  <findings>
    <finding>
      <location>...</location>
      <issue>undocumented_scarcity|manufactured_urgency</issue>
      <required_fix>...</required_fix>
    </finding>
  </findings>
</bbos_validator_output>
