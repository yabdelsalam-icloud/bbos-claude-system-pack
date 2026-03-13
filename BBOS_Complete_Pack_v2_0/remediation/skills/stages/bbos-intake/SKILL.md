---
name: bbos-intake
description: Process Stage 00 INT operator self-assessment and Stage 00.1 IFB intake form build. The default startup stage for every new BBOS session without existing valid state.
---

# BBOS Stage Skill — INT / IFB

## Purpose
Process the operator self-assessment (Stage 00 INT) and, when required, build the intake form instrument (Stage 00.1 IFB). This is the foundation stage. Everything above it depends on the honesty of what is established here.

## Stage identity
Stages: `00_INT` and `00.1_IFB`

Allowed anchors:
- `@@BBOS_STAGE:INT@@`
- `@@BBOS_STAGE:IFB@@`
- `@@SECTION:CANON@@`
- `@@SECTION:RESEARCH_FACTORY@@`
- `@@SECTION:ASSET_FACTORY@@`
- `@@SECTION:ASSEMBLE_CONTRACT@@`
- `@@SECTION:SPIRITUAL_ANCHOR@@` — only when ANNOTATE is explicitly invoked

## The six intake sections

Every intake must cover all six sections. No section may be omitted or deferred.

| # | Section | What is being established |
|---|---------|--------------------------|
| 1 | Capital | Financial Stewardship Horizon — honest runway projection before requiring external capital or achieving principle-driven profitability. Not best-case. The number that is actually true. |
| 2 | Skills | Core competency and operational expertise. Verifiable, not aspirational. |
| 3 | Proof | Integrity proof links — verifiable references that substantiate claimed competencies and results. |
| 4 | Constraints | 3–5 Non-Negotiable Work Aversions and any fixed constraints on time, capital, or capacity. |
| 5 | Geography | Specific preferred geographic area, associated commercial/industrial zoning context. |
| 6 | Regulatory | Known regulatory, licensing, or compliance requirements relevant to the intended work. |

## You must

**For INTAKE command:**
- Capture the operator's intake answers exactly as provided — do not reframe or improve them.
- Produce the Normalised Intake Packet in field order (Capital → Skills → Proof → Constraints → Geography → Regulatory).
- Flag every field where the answer does not clearly map to the required data.
- Produce a Gap Check that lists each missing or ambiguous field with: what is missing, why it is required, and what specific information would close the gap.
- Issue a Routing Decision: route to Stage 01 QAL if the intake is sufficiently complete and no automatic disqualifiers are present, or output NO-SHIP — INTAKE INCOMPLETE with specific missing items listed.

**For ASSEMBLE command (Stage 00.1 IFB):**
- Produce the BBOS-to-Form Mapping Guide: each intake section mapped to one or more form questions.
- Produce the Reformatted Intake Questionnaire Template.
- Produce Field Validation Rules: required/optional flags, conditional visibility, disqualifier logic.
- Produce a Form Version Log entry.

## You must not
- Route optimistically. If the intake is borderline, output the gap check and require the operator to complete missing information before routing proceeds.
- Infer missing intake data from context. A gap is a gap. Name it and wait.
- Proceed to Stage 01 QAL if any automatic disqualifier is present.
- Design intake form questions that lead respondents toward desired answers or make it easier to overstate capacity.
- Generate strategic assets, offer language, or positioning — those begin at Stage 01.
- Auto-generate spiritual annotations. ANNOTATE must be explicitly invoked.

## Automatic disqualifiers (route to Stage 01.1 REJ)
Route to Stage 01.1 REJ — not forward to QAL — if any of the following is present:
- Operator cannot provide verifiable proof for at least two claimed competencies.
- Financial Stewardship Horizon is zero or unspecified (no documented runway exists).
- Stated constraints make the target work category operationally impossible.

Routing to Stage 01.1 is not a failure. It is an act of stewardship toward the operator's real situation.

## Required inputs
For Stage 00 INT:
- Operator's completed intake answers (all six sections, or partial — gaps will be flagged)

For Stage 00.1 IFB:
- Completed Normalised Intake Packet from Stage 00 INT
- Any existing form drafts or question sets

## Stage 00 asset pack contents
- Completed Normalised Intake Packet — all six sections mapped and gap-checked
- Routing Decision — documented with specific basis (which fields confirmed completion, which gaps remain, whether disqualifiers were present)

## Stage 00.1 asset pack contents
- BBOS-to-Form Mapping Guide — field-by-field alignment document
- Reformatted Intake Questionnaire Template
- Field Validation Rules — required/optional flags, conditional visibility, disqualifier logic
- Form Version Log Entry — form link, version number, deployment date

## Completion criteria (Stage 00 INT)
- All six intake sections present and mapped
- No fields are ambiguous without documented flag
- Gap Check is complete — all gaps named with resolution path
- Routing Decision is issued with explicit basis
- No automatic disqualifier is present (or, if present, REJ is correctly invoked)

## Completion criteria (Stage 00.1 IFB)
- Mapping guide covers all six intake sections
- Every form field has a required/optional designation
- Disqualifier logic is documented and testable
- Version log entry is present

## NO_SHIP conditions
Return no_ship if:
- No intake data has been provided
- The active stage is unclear and no explicit stage has been named
- Cross-stage mixing is requested (e.g., building offer language during intake)
- Guessing would be required to fill intake gaps
- A routing decision is requested before all six sections are at minimum attempted

## Spiritual annotation placement (when ANNOTATE is explicitly invoked)
- Before the Normalised Intake Packet: ⧁ Ash-Shahid — the operator writes before the One who already knows the accurate version of every answer.
- Before the Gap Check: ⧁ Ash-Shahid — what is withheld is not hidden.
- Before the Routing Decision: ⧁ Al-Awwal — this is the foundation being laid. A routing made honestly, including routing to incompleteness when incompleteness is present, is the system beginning rightly.
- For Stage 00.1 IFB form design: ⧁ Ash-Shahid — the form invites another person toward honest self-disclosure. Design questions that serve honest disclosure, not the system's preferred outcomes.

All annotations: 2 sentences maximum. One specific operational implication. Do not repeat the same attribute twice in one output.

## Required output schema
Return exactly:

```xml
<bbos_stage_output>
  <stage>00_INT</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="all_six_sections_attempted">met|not_met</criterion>
    <criterion name="gap_check_complete">met|not_met</criterion>
    <criterion name="no_automatic_disqualifier">met|not_met</criterion>
    <criterion name="routing_decision_issued">met|not_met</criterion>
  </criteria_report>
  <missing_inputs>
    <item>...</item>
  </missing_inputs>
  <blocking_issues>
    <issue>...</issue>
  </blocking_issues>
  <updated_asset>
    <!-- Normalised Intake Packet, Gap Check, and Routing Decision -->
    ...
  </updated_asset>
</bbos_stage_output>
```

For Stage 00.1 IFB, set `<stage>00.1_IFB</stage>` and include form deliverables inside `<updated_asset>`.
