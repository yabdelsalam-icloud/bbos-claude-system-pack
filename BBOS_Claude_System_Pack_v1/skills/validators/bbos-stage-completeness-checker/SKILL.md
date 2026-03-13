---
name: bbos-stage-completeness-checker
description: Verify that all canon-required assets for the active stage are present and structurally complete.
---

# BBOS Validator — Stage Completeness Checker

## Purpose
Check that the stage output contains all required deliverables and that each deliverable is structurally complete.

## You must
- identify the active stage
- compare the output against the stage deliverables checklist
- flag missing sections and structurally incomplete sections

## You must not
- waive missing deliverables because adjacent assets look strong
- approve placeholder sections as complete

## Required output schema
Return exactly:

<bbos_validator_output>
  <validator>bbos-stage-completeness-checker</validator>
  <status>pass|fail</status>
  <findings>
    <finding>
      <location>...</location>
      <issue>missing_deliverable|structurally_incomplete</issue>
      <required_fix>...</required_fix>
    </finding>
  </findings>
</bbos_validator_output>
