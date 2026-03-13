# BBOS Claude System Pack v1

This package contains a Claude-native implementation scaffold for BBOS.

## Included
- Runtime governance layer
- Stage skills
- Specialist skills
- Validator skills
- Shared schemas
- Project state scaffold
- Source basis notes for each major module family

## First production set
- governor/SKILL.md
- stages/bbos-offer/SKILL.md
- validators/bbos-glabel-auditor/SKILL.md
- specialists/bbos-copywriting-architect/SKILL.md

## Next production set
- stages/bbos-outreach/SKILL.md
- stages/bbos-sales/SKILL.md
- specialists/bbos-sales-script-builder/SKILL.md
- specialists/bbos-content-idea-engine/SKILL.md
- specialists/bbos-hook-library-builder/SKILL.md
- specialists/bbos-objection-response-builder/SKILL.md
- validators/bbos-truth-gate-validator/SKILL.md
- validators/bbos-scarcity-checker/SKILL.md
- validators/bbos-stage-completeness-checker/SKILL.md

## Design principle
Router/Governor -> Active Stage Skill -> Specialist Skill(s) -> Validator Skill(s) -> Aggregation Decision -> State Update

## Notes
- Spiritual annotations are explicit-invocation only.
- Specialist skills serve stages; they do not govern stages.
- Validators are separated from generators.
- The project state object lives outside the model.

See `docs/architecture_overview.md` for the full operating picture.
