# BBOS Claude Architecture Overview

## Operating hierarchy
1. Runtime Governor
2. Active Stage Skill
3. Specialist Skill(s), if allowed by stage
4. Validator Skill(s)
5. Aggregation + state update

## Why this shape
BBOS already separates runtime governance from stage canon and factories.
Claude should execute bounded modules rather than act as one giant master prompt.

## Runtime rules carried into this architecture
- Start in intake mode unless valid state says otherwise
- Never mix stages
- Use only approved anchors for the active command
- Output NO_SHIP when required inputs are missing or guessing would be required
- Never auto-generate the spiritual layer
- Keep annotations operator-facing only

## Recommended first pilot
Stage 03 (Offer):
- governor
- bbos-offer
- bbos-glabel-auditor
- bbos-copywriting-architect

## Recommended second pilot
Stage 04/05:
- bbos-outreach
- bbos-sales
- bbos-sales-script-builder
- bbos-hook-library-builder
- bbos-objection-response-builder
- bbos-truth-gate-validator
- bbos-scarcity-checker
