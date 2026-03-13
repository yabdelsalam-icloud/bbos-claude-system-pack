---
name: bbos-opt
description: Execute Stage 08 OPT (Optimization). Reviews the four Canonical Metrics, completes the Stewardship Score (MG-01), Barakah Health Index (MG-03), and Team Vitality Score (DRIFT-03). Identifies the weakest link, builds the optimization action set, and closes the cycle with a versioned document log and a next-cycle test plan. Runs at the close of every complete BBOS cycle.
version: 1.0
---

# BBOS Stage Skill — OPT

## Purpose
Close the cycle with honest reckoning. Review what actually happened across CM-1 through CM-4. Score the operator's stewardship state from behavioural evidence, not aspiration. Identify the single weakest link in the system, build three targeted actions to address it, and document what changes and what must not change this cycle. Then prepare the next cycle's primary test.

The governing orientation of this stage is muhasaba — honest self-accounting before the One who already knows. Al-Hasib sees the true value of every action independent of how it is presented. The OPT output is not a performance review for an audience. It is a reckoning for the operator.

---

## Stage identity

Stage: `08_OPT`

Allowed anchors:
- `@@BBOS_STAGE:OPT@@`
- `@@SECTION:CANON@@`
- `@@SECTION:RESEARCH_FACTORY@@`
- `@@SECTION:ASSET_FACTORY@@`
- `@@SECTION:ASSEMBLE_CONTRACT@@`
- `@@SECTION:SPIRITUAL_ANCHOR@@` — only when ANNOTATE is explicitly invoked

**Note:** Stage 08 has no confirmed spiritual annotation placement points for auto-generation. ANNOTATE invoked at OPT will return NO_SHIP unless the operator specifies the exact section from the list below under Spiritual Annotation Placement.

---

## Canon principles (non-negotiable)

**Score from evidence, not aspiration.** The Stewardship Score (MG-01) is the band where the majority of observable behavioural evidence sits — not the band the operator would score if performing well-being. Scoring aspirationally is not optimism. It is a form of self-concealment practised before the One from whom nothing is concealed.

**The Restoration Mandate is not a bypass.** If the Stewardship Score falls below 7.0 on Cycle 3 or later, G7.2 applies. The Constrained Proceed Protocol (FP-01) is an accountable exception path, not a workaround. Type A depletion has no exception.

**The Weakest Link is one thing.** The OPT cycle produces one identified weakest link, traced to one specific stage and asset. Optimizing everything is optimizing nothing. The three actions all serve the one link.

**The Hold List is as important as the action list.** Changing too many things at once makes it impossible to know what worked. The Hold List protects the rest of the system while the targeted test runs.

**Canonical Metrics are not replaceable.** CM-1 through CM-4 must all appear in every OPT cycle output. Operating without a canonical metric for more than two consecutive cycles is a system integrity breach.

---

## Required inputs

- All four Canonical Metric values for the current cycle (CM-1, CM-2, CM-3, CM-4)
- Prior cycle's OPT output (for period-over-period comparison)
- Stewardship Score self-assessment with behavioural evidence for each dimension
- BHI ratings (BHI-1 through BHI-5)
- Team Vitality responses (TV-1, TV-2, TV-3) — collected anonymously before the OPT session
- All BBOS stage documents currently in use (for the Document Version Log)

If any required input is missing: return NO_SHIP with the specific item and resolution path. Do not estimate or substitute.

---

## Research Factory (S-OUTPUTS)

Run before ASSEMBLE. Produces the analytical foundation for the optimization pack.

**PROMPT 08.R1 — Metric Review**
Review all four Canonical Metrics against prior cycle values. For each:
- Current value vs. prior cycle
- Direction (improving / declining / stable)
- What the movement indicates about the specific stage it measures

| Metric | Definition | Measurement | What failure indicates |
|---|---|---|---|
| CM-1 — Qualified Outreach Conversion Rate | % of outreach recipients who take the defined first action | (# qualifying first actions) / (# outreach contacts) × 100 | Stage 04 OUT content, targeting, or lead source misaligned. Enemy Narrative or Belief Statement not resonating. |
| CM-2 — Fit-to-Close Rate | % of completed Fit Calls resulting in signed agreement or deposit within 14 days | (# closed agreements within 14 days) / (# completed Fit Calls) × 100 | Stage 05 SAL offer framing, objection handling, or qualification criteria misaligned. |
| CM-3 — Client Milestone Completion Rate | % of active clients reaching each defined Client Success Milestone (FUL_S3) on schedule, measured at midpoint | (# clients at or ahead of midpoint milestone) / (# active clients) × 100 | Stage 06 FUL Execution SOP, client intake constraints, or capacity planning failing. |
| CM-4 — Unprompted Referral Rate | % of completed engagements producing at least one unprompted referral in 90-day rolling window | (# engagements producing ≥1 unprompted referral in 90 days) / (# engagements completed in period) × 100 | Client experience is adequate but not remarkable. Barakah alignment of the work is missing. |

**PROMPT 08.R2 — Weakest Link Identification**
Identify the single metric with the largest gap between current performance and its health threshold. Trace the root cause to one specific stage and one specific asset within that stage. Produce one testable hypothesis for what is causing the underperformance.

**PROMPT 08.R3 — Barakah Health Index (MG-03)**
Score BHI-1 through BHI-5. Produce Overall Reading: ALIGNED / MONITORING / INVESTIGATE.

| Indicator | What it measures | Healthy range | Early warning signal |
|---|---|---|---|
| BHI-1 — Unprompted Referral Rate | Whether work produces genuine excess value that clients share without being asked (overlaps CM-4 intentionally — tracked here as a Barakah signal, not a business metric) | ≥ 20% of completed engagements in rolling 90 days | Rate drops below 10% for two consecutive cycles |
| BHI-2 — Operator Post-Work Energy Rating | Whether the work itself is generative or depleting, distinct from the Stewardship Score | Average ≥ 7.0 over the cycle | Average drops below 6.0 for one cycle or below 7.0 for two consecutive cycles — revisit S4 Energy Profile |
| BHI-3 — Right-Fit Client Ratio | Whether the business is attracting clients matching the ICP defined at Stage 03 OFR Asset 2 | ≥ 70% of active client base | Drops below 50% in any single cycle — ICP definition needs revision or Stage 04/05 targeting has drifted |
| BHI-4 — Decision Clarity Rate | Whether major decisions were made from strategic clarity or rationalisation (Clarity / Considered / Rationalised) | ≥ 80% of decisions in Clarity or Considered categories | More than 20% in Rationalised — scarcity or pressure is infiltrating decision-making |
| BHI-5 — Asset Integrity Currency | Whether active client-facing assets remain G-label compliant as the business grows | 10/10 or 9/10 in spot checks | Any asset requiring significant correction, or two consecutive cycles with 3+ minor corrections in the sample |

**PROMPT 08.R4 — Team Vitality Score (DRIFT-03)**
Aggregate the anonymous TV-1, TV-2, TV-3 responses. Produce averages and routing action per dimension.

| Dimension | Question | Low score signal |
|---|---|---|
| TV-1 — Work Sustainability | "How sustainable is your current workload this week — where 1 is I cannot keep this up and 10 is I could operate like this indefinitely?" | Average below 6: capacity or resourcing issue in Stage 06 FUL. Review Execution SOP and operator capacity constraints in OFR Scope Map. |
| TV-2 — Clarity of Purpose | "How clear are you on what we are building and why it matters — where 1 is I have no idea and 10 is completely clear?" | Average below 6: onboarding, briefing, or communication of the strategic foundation is failing. |
| TV-3 — Trust in Leadership | "How much do you trust that decisions being made are genuinely in the team's and clients' best interests — where 1 is not at all and 10 is completely?" | Average below 6: systemic signal requiring direct operator attention before the next OPT cycle. |

**PROMPT 08.R5 — Stewardship Score (MG-01)**
Score from the band where the majority of behavioural evidence sits. Not the aspirational band. If the score is below 7.0, apply the Restoration Mandate rules:

- Cycles 1–2: Constrained Proceed Protocol (FP-01) required. Active operator choice documented.
- Cycle 3+: G7.2 full Restoration Mandate applies unless FP-01 exception is documented with evidence.
- Type A depletion (existential): no exception. Standard G7.2 applies.
- Type B (situational fatigue, score 5–6.9, no missed obligations): FP-01 permitted with full Stage 2 and 3 completion.
- Type C (score ≥ 7.0 with constraints): FP-01 permitted with full Stage 2 and 3 completion.

Every third cycle (3, 6, 9…): the Stewardship Score must be reviewed with a named accountability contact. Their single question — "What is the evidence for the score you gave yourself on the dimension you rated lowest?" — is recorded in one sentence in the Version Log.

---

## Asset Factory: OPT Optimization Pack (ASSEMBLE)

All ten items must be present before `<decision>ready</decision>` is returned.

| # | Item | Specification |
|---|---|---|
| 1 | Metric Dashboard | All four CM values with current period, prior period, direction, and what the movement indicates. No estimated values. |
| 2 | Weakest Link | One identified metric, the specific stage it maps to, the specific asset within that stage, and the root cause hypothesis. One hypothesis. |
| 3 | Root Cause Hypothesis | One testable statement: "If [specific change is made to specific asset at specific stage], then [metric] will move in [direction] by [next cycle]." Falsifiable. |
| 4 | Top 3 Optimization Actions | Three actions, each scoped to a specific stage and a specific asset. No vague directives. Each action names: what changes, where it changes, who owns it, and when it will be complete before the next OPT cycle. |
| 5 | Document Version Log | Named documents with described changes made this cycle. One sentence per document. No changes = no entry. |
| 6 | Hold List | What must not be changed this cycle. Every item on the Hold List is there to prevent confounding the primary test. Minimum: everything not touched by the Top 3 Optimization Actions. |
| 7 | Stewardship Score | Behaviourally-anchored score with evidence summary for the lowest-rated dimension. Restoration Mandate status (active / not triggered / FP-01 documented). |
| 8 | Barakah Health Index | BHI-1 through BHI-5 with current values, and Overall Reading: ALIGNED / MONITORING / INVESTIGATE. If INVESTIGATE: the investigation prompt for the next Weakest Link session. |
| 9 | Team Vitality Score | TV-1, TV-2, TV-3 averages with routing action for any dimension below 6. |
| 10 | Next Cycle Test Plan | One primary test. Includes: hypothesis being tested, success criteria (specific metric movement), timeline, and what unchanged items protect the test's integrity. |

---

## Completion criteria

- All four CM values present with current and prior-cycle comparison
- Weakest Link traced to one specific stage and one specific asset
- Root Cause Hypothesis is falsifiable and scoped to next cycle
- Three Optimization Actions are stage-scoped and asset-specific
- Stewardship Score from behavioural evidence — aspirational band not used
- Restoration Mandate status documented if score is below 7.0
- BHI Overall Reading produced
- TVS averages and routing action for any dimension below 6
- Hold List covers everything not targeted by the three actions
- Next Cycle Test Plan has defined success criteria

---

## NO_SHIP conditions

Return `no_ship` if:
- Any of CM-1 through CM-4 are absent — the Metric Dashboard cannot be produced without all four
- Prior cycle OPT output is absent for Cycle 2+ — period-over-period comparison is not possible
- Stewardship Score would be produced without behavioural evidence (aspirational scoring is not permitted)
- BHI-1 through BHI-5 responses are absent
- Team Vitality responses (TV-1, TV-2, TV-3) were not collected before the session — aggregate cannot be produced without them
- The request requires generating new stage assets (offer, outreach, sales, fulfillment work) — that is not OPT scope

---

## Spiritual annotation placement (when ANNOTATE is explicitly invoked)

Governing attributes: **Al-Hasib · As-Subbuh · Al-Quddus**

These are the only three valid annotation placement points at Stage 08. If ANNOTATE is invoked for any other section, return NO_SHIP: "No spiritual anchor exists for [section] at Stage 08."

- Before Stewardship Score / MG-01: ⧁ Al-Hasib — the reckoning is already complete. The Stewardship Score is produced for the operator's own honest accounting before God, not for the system. Scoring from the evidential band is the practice of honesty before the One from whom nothing is concealed.
- Before Barakah Health Index / MG-03: ⧁ Al-Hasib — the BHI asks the operator to notice what is actually present, not what is performing well in a report. BHI-2 in particular cannot be engaged honestly from a performing posture. It requires the same quality of self-observation as the Stewardship Score.
- Before Restoration Mandate / FP-01: ⧁ As-Subbuh / Al-Quddus — the pause is an act of taqdis, not an admission of failure. A source that has been depleted cannot produce Barakah regardless of how much it continues to output. Honouring the Mandate is choosing genuine Barakah over contaminated output.

All annotations: 2 sentences maximum. One specific operational implication. Use only Al-Hasib and As-Subbuh / Al-Quddus — do not import attributes from other stages.

---

## Required output schema

```xml
<bbos_stage_output>
  <stage>08_OPT</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="all_four_cm_values_present">met|not_met</criterion>
    <criterion name="weakest_link_traced_to_stage_and_asset">met|not_met</criterion>
    <criterion name="root_cause_hypothesis_falsifiable">met|not_met</criterion>
    <criterion name="three_actions_stage_and_asset_scoped">met|not_met</criterion>
    <criterion name="stewardship_score_from_behavioural_evidence">met|not_met</criterion>
    <criterion name="restoration_mandate_status_documented">met|not_met</criterion>
    <criterion name="bhi_overall_reading_produced">met|not_met</criterion>
    <criterion name="tvs_routing_action_for_low_dimensions">met|not_met</criterion>
    <criterion name="hold_list_present">met|not_met</criterion>
    <criterion name="next_cycle_test_plan_with_success_criteria">met|not_met</criterion>
  </criteria_report>
  <missing_inputs>
    <item>...</item>
  </missing_inputs>
  <blocking_issues>
    <issue>...</issue>
  </blocking_issues>
  <updated_asset>
    <!-- Complete OPT Pack in order:
         1. Metric Dashboard (CM-1–CM-4)
         2. Weakest Link
         3. Root Cause Hypothesis
         4. Top 3 Optimization Actions
         5. Document Version Log
         6. Hold List
         7. Stewardship Score (MG-01)
         8. Barakah Health Index (MG-03, BHI-1–5)
         9. Team Vitality Score (TV-1–3)
         10. Next Cycle Test Plan -->
    ...
  </updated_asset>
</bbos_stage_output>
```
