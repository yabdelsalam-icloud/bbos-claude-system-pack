---
name: bbos-qal
description: Execute Stage 01 QAL (Qualification & Alignment) and Stage 01.1 REJ (Rejection). Runs the Amanah Intake Screening Rubric, produces the six-pillar Strategic Mandate (S1–S6), completes the Viability Pre-Check (V1–V3), and assembles the QAL Asset Pack. Gates the entire forward progression — nothing advances to Stage 02 STR without this stage clearing.
version: 1.0
---

# BBOS Stage Skill — QAL / REJ

## Purpose
Produce the Qualification & Alignment asset pack that forms the strategic and ethical foundation for everything above it. This stage has two jobs: screen for fitness before any strategic work begins, and then synthesise what is honestly present into the six pillars that will ground every subsequent stage.

If a candidate does not clear the screening rubric, this skill routes to Stage 01.1 REJ with dignity and specificity — not avoidance.

---

## Stage identity

Stages: `01_QAL` and `01.1_REJ`

Allowed anchors:
- `@@BBOS_STAGE:QAL@@`
- `@@BBOS_STAGE:REJ@@`
- `@@SECTION:CANON@@`
- `@@SECTION:RESEARCH_FACTORY@@`
- `@@SECTION:ASSET_FACTORY@@`
- `@@SECTION:ASSEMBLE_CONTRACT@@`
- `@@SECTION:SPIRITUAL_ANCHOR@@` — only when ANNOTATE is explicitly invoked

---

## Canon principles (non-negotiable)

**Viability Gate Primacy.** All niche candidates must pass the four foundational Viability Gates (A–D) before any scoring or valuation work begins. Integrity first, opportunity second. A candidate that cannot pass Gates A–D does not receive a score. It receives a routing to 01.1 REJ.

**No External Assumption.** The system will not invent or attribute operator skills that are not explicitly and verifiably stated in the intake data and proof links. If it is not in the intake, it does not exist for the purposes of this stage.

**Amanah Proof Audit.** All claimed proof is evaluated for strength and verifiability. Weak or non-verifiable proof cannot justify G1/G2 claims later in the system. Gaps in proof are named, not smoothed over.

**Pipeline anxiety does not soften hard stops.** The Automatic Disqualifiers in the Screening Rubric exist to protect both the operator and the applicant from proceeding on a foundation that cannot hold. A thin pipeline is not a reason to pass a candidate that should be rejected.

---

## Execution sequence

QAL must be executed in this order. Do not skip or reorder steps.

```
1. Amanah Intake Screening Rubric (FP-02)
        ↓
   [ Any ★ triggered? → Route to 01.1 REJ immediately ]
   [ 5+ non-disqualifier NOs? → Route to 01.1 REJ ]
   [ 3–4 NOs? → Escalate to founder before proceeding ]
        ↓
2. Research Factory — S1 through S6
        ↓
3. Viability Pre-Check — V1, V2, V3 (Gates A–D)
        ↓
   [ Any niche fails Gates A–D? → Log in V2 Removed Niche Log ]
        ↓
4. Asset Factory — Assets 1 through 5
        ↓
5. QAL Asset Pack complete → Governor recommends advance to 02 STR
```

---

## Step 1 — Amanah Intake Screening Rubric (FP-02)

Run this rubric before S1–S6 synthesis begins. Score each question YES or NO based only on the information available from the Stage 00 intake data. No inference. No benefit of the doubt.

| # | Screening question | Answer | Flag |
|---|---|---|---|
| 1 | Has the applicant provided verifiable proof (links, references, documented history) for at least two of the claimed competencies in their intake? | YES / NO | NO = Weak proof flag |
| 2 | Can the operator's stated regulatory compliance in their target geography be independently verified or confirmed? | YES / NO | NO = Regulatory flag |
| 3 ★ | Does the applicant's stated business model require the BBOS operator to make claims the operator cannot directly verify or substantiate? | YES / NO | YES = AUTO-DISQUALIFY |
| 4 | Is the applicant's Financial Stewardship Horizon (runway) sufficient to reach the first revenue milestone without requiring undisclosed or predatory external capital? | YES / NO | NO = Viability flag |
| 5 ★ | Has the applicant stated or implied intent to use BBOS-produced assets in a geography or sector where the operator lacks regulatory clearance? | YES / NO | YES = AUTO-DISQUALIFY |
| 6 | Does the applicant's niche focus align with the operator's stated core competency (S1) without requiring competencies not present in the intake? | YES / NO | NO = Competency misalignment flag |
| 7 | Is the applicant's energy and capacity profile (S4) realistic for the delivery requirements of their stated niche? | YES / NO | NO = Capacity flag |
| 8 ★ | Has the applicant provided false, incomplete, or materially inconsistent information at any point in the intake process? | YES / NO | YES = AUTO-DISQUALIFY |
| 9 | Does the applicant demonstrate a basic understanding of what the BBOS operator's role is and is not? | YES / NO | NO = Expectation misalignment flag |
| 10 | Given all constraints (S5), is there a realistic path to delivering the promised outcome within the operator's current capacity? | YES / NO | NO = Delivery viability flag — escalate |

**Rubric routing rules:**

| Rubric result | Action |
|---|---|
| Any ★ Automatic Disqualifier triggered | Route to Stage 01.1 REJ immediately. State the specific question that triggered rejection. Produce Responsible Removal Log entry. |
| 0–2 non-disqualifier NOs | Proceed to QAL. Brief written summary to founder (notification, not approval). |
| 3–4 non-disqualifier NOs | Escalate to founder. Present the flags. Founder decision required before Stage 01 proceeds. |
| 5+ non-disqualifier NOs | Route to Stage 01.1 REJ. Rationale: insufficient alignment across multiple integrity dimensions. |

---

## Step 2 — Research Factory: S1–S6 (Six Pillars of the Strategic Mandate)

Produce these six outputs in order. Each is grounded only in what is explicitly present in the intake data and verified proof links.

| Output | Description |
|---|---|
| S1 — Core Competency | A precise, evidence-backed definition of the operator's highest-leverage skill or unique operational expertise. The singular capability that forms the bedrock of the potential business model. Not aspirational — grounded in S3 proof. |
| S2 — Advantage Register | The operator's sustainable, principle-driven competitive advantage derived from S1 in the context of their target market. The moat built on integrity, not imitation. |
| S3 — Integrity Proof Audit | A detailed, objective assessment of the proof links provided. Quantifies the reliability, scope, and direct ethical relevance of each piece of evidence. Highlights gaps explicitly — does not paper over them. |
| S4 — Energy Profile | A psychological and operational map based on the intersection of Core Competency (S1) and the operator's Work Aversions. Identifies energy-generating vs. energy-depleting activities. Designed for operator longevity, not just output. |
| S5 — Constraint Map | A comprehensive outline of all significant limitations and obstacles. Includes Financial Stewardship Horizon, proof gaps from S3, regulatory hurdles, and resource dependencies. Critical for risk integrity downstream. |
| S6 — Regulatory Baseline | A distilled summary of the essential permits, licenses, zoning compliance requirements, and operational standards mandated by the target geography and sector. |

**Required inputs for S1–S6:**
- Stage 00 Normalised Intake Packet (all six sections complete)
- Integrity Proof Links — verifiable, hyperlinked references substantiating claimed competencies
- If either is missing: return NO_SHIP, list what is missing and why it is required

---

## Step 3 — Viability Pre-Check: V1, V2, V3

Run Gates A–D for each niche candidate before any scoring begins. A candidate that fails any gate is removed and logged. It does not receive a score.

**The four Viability Gates:**

| Gate | What it checks | Fail condition |
|---|---|---|
| Gate A — Regulatory Clearance | Operator has confirmed clearance to operate in the target geography and sector | Regulatory status unverifiable or clearance absent |
| Gate B — Addressable Market Fit | A real, reachable market exists for the niche within operator's geography | Market is theoretical or inaccessible given operator constraints |
| Gate C — Certification / Competence Proof | Operator holds or can verifiably obtain required credentials for the niche | Credentials absent and no documented path to obtain them |
| Gate D — Proven Demand | Evidence of actual demand exists — not assumed, not projected from general trends | Demand is assumed without documentary basis |

**Viability Pre-Check outputs:**

| Output | Contents |
|---|---|
| V1 — Viability Gate Results Table | Each niche candidate scored against Gates A–D. Pass/fail per gate. Overall pass/fail per candidate. |
| V2 — Removed Niche Log | Every niche candidate that failed any gate, with the specific gate that triggered removal and the specific reason. |
| V3 — Cleared Candidate Handoff | The list of niche candidates that passed all four gates, formatted for use in the Asset Factory scoring step. |

If no niche candidates pass all four gates: return NO_SHIP — VIABILITY GATE: NO CLEARED CANDIDATES. List the closest candidates with their specific gate failures and what would be required to clear each gap.

---

## Step 4 — Asset Factory: Assets 1–5

Produce these five outputs using only cleared candidates from V3 and grounded in S1–S6.

| Asset | Description |
|---|---|
| Asset 1 — Offer Category Match | Maps each cleared niche candidate to the most appropriate BBOS offer category (productised service, retainer, course, done-with-you, etc.) based on S1 competency and S4 energy profile. |
| Asset 2 — Niche Candidates Scored | Each cleared candidate evaluated across: competency alignment, market accessibility, proof strength, operator energy fit, regulatory clarity, revenue potential within runway. Scored 1–5 per dimension. |
| Asset 3 — Niche Scoring Matrix | Full scoring matrix for all cleared candidates. Dimensions weighted by operator constraints from S5. Top candidate(s) identified. |
| Asset 4 — Score Pattern Analysis | What the scores reveal about the operator's genuine strengths, blind spots, and where the system will be most generative vs. most strained. Honest analysis — not encouragement. |
| Asset 5 — Amanah Proof Audit | A final verification that the top-ranked niche(s) can be pursued without claims exceeding what the proof in S3 can support. Flags any dimension where the score is higher than the proof can justify. Produces proof gap list for the operator to close before Stage 03 OFR. |

---

## Stage 01.1 REJ — Rejection

When routing to REJ, this skill produces:

1. **Rejection basis** — the specific rubric question(s) or viability gate(s) that triggered the routing. Precise. No vague language.
2. **Responsible Removal Log entry** — documents: the candidate, the trigger, the date, the specific reason, and what would need to change for a future re-application to be considered.
3. **Operator-facing summary** — written with dignity. The rejection is an act of protection, not punishment. The language does not soften the no, but it does not demean the person either.

REJ is a terminal exit for the current candidate in the current cycle. The operator does not advance to Stage 02 on the basis of a rejected candidate.

---

## You must

- Run the Screening Rubric before any research or asset work begins.
- Produce S1–S6 grounded only in explicitly verified intake data.
- Apply Gates A–D to every niche candidate before scoring begins.
- Name proof gaps rather than filling them with aspiration.
- Route to 01.1 REJ when the rubric or viability gates require it — regardless of pipeline pressure.
- Produce the Responsible Removal Log for every REJ routing.
- Keep all scoring in Assets 2–3 grounded in S1–S6 evidence, not operator desire.

## You must not

- Invent or attribute competencies not present in the intake and proof links.
- Score a candidate that has not passed all four Viability Gates.
- Soften an Automatic Disqualifier trigger with "probably not quite yes."
- Advance to Asset Factory work before S1–S6 are complete.
- Perform any Stage 02 STR or Stage 03 OFR work — those stages begin only after the QAL Asset Pack is approved.
- Issue a `ready` decision if the Amanah Proof Audit (Asset 5) identifies proof gaps on the top-ranked niche — flag them as blocking until the operator closes them.

---

## Required inputs

- Stage 00 Normalised Intake Packet (all six sections)
- Integrity Proof Links (at minimum two verifiable references for claimed competencies)
- Operator's niche candidate list (may be derived from intake if not explicitly provided)

If any required input is missing: return NO_SHIP with the specific missing item, why it is required, and what information would resolve the gap.

---

## QAL Asset Pack contents (completion checklist)

- [ ] Screening Rubric (FP-02) — scored with routing decision and basis documented
- [ ] S1 — Core Competency
- [ ] S2 — Advantage Register
- [ ] S3 — Integrity Proof Audit (with explicit proof gaps listed)
- [ ] S4 — Energy Profile
- [ ] S5 — Constraint Map
- [ ] S6 — Regulatory Baseline
- [ ] V1 — Viability Gate Results Table
- [ ] V2 — Removed Niche Log (may be empty if no candidates were removed)
- [ ] V3 — Cleared Candidate Handoff
- [ ] Asset 1 — Offer Category Match
- [ ] Asset 2 — Niche Candidates Scored
- [ ] Asset 3 — Niche Scoring Matrix
- [ ] Asset 4 — Score Pattern Analysis
- [ ] Asset 5 — Amanah Proof Audit (with proof gap list for Stage 03 OFR)

All 15 items must be present and complete before `<decision>ready</decision>` is returned.

---

## Completion criteria

- Screening Rubric run and routing decision documented
- No unresolved Automatic Disqualifier triggers
- S1–S6 produced from verified intake data only, with no invented attributes
- All niche candidates evaluated against Gates A–D before scoring
- At least one candidate cleared all four Viability Gates
- Assets 1–5 complete and grounded in S1–S6
- Amanah Proof Audit complete — proof gaps listed and flagged for Stage 03
- No claim in the asset pack exceeds what the S3 proof can support

---

## NO_SHIP conditions

Return `no_ship` if:
- Stage 00 Normalised Intake Packet is absent or incomplete
- Integrity Proof Links are absent (cannot run S3 or Asset 5 without them)
- An Automatic Disqualifier is triggered (route to 01.1 REJ, not forward)
- No niche candidate passes all four Viability Gates
- S1–S6 would require inventing competencies not present in the intake
- The request requires guessing about any screening, viability, or scoring dimension

---

## Spiritual annotation placement (when ANNOTATE is explicitly invoked)

- Before the Amanah Gate or any Go/No-Go framing: ⧁ Al-Haqq — the operator is building a foundation. This is the moment to declare whether it is built on truth or on aspiration dressed as fact.
- Before S4 Energy Profile and S5 Constraint Map: ⧁ Al-Khabir — God already knows the hidden exhaustion and the runway shorter than stated. Candor here is an act of worship.
- Before Automatic Disqualifiers in the Screening Rubric: ⧁ Al-Haqq — pipeline anxiety must not soften a hard no. A disqualification honoured protects the Barakah of everything that follows.
- Before V1 Viability Gate Results: ⧁ Al-Haqq — a pass that is not genuinely earned is a deferred failure.
- Before Asset 3 Niche Scoring Matrix (operator capacity scores): ⧁ Al-Khabir — the score that reflects honest capacity is the score that carries Barakah forward.

All annotations: 2 sentences maximum. One specific operational implication. Do not repeat the same attribute twice in the same output.

---

## Required output schema

```xml
<bbos_stage_output>
  <stage>01_QAL</stage>
  <decision>ready|not_ready|no_ship</decision>
  <criteria_report>
    <criterion name="screening_rubric_complete">met|not_met</criterion>
    <criterion name="no_auto_disqualifier_triggered">met|not_met</criterion>
    <criterion name="s1_s6_grounded_in_verified_intake">met|not_met</criterion>
    <criterion name="viability_gates_applied_before_scoring">met|not_met</criterion>
    <criterion name="at_least_one_candidate_cleared_gates">met|not_met</criterion>
    <criterion name="assets_1_5_complete">met|not_met</criterion>
    <criterion name="amanah_proof_audit_complete">met|not_met</criterion>
    <criterion name="proof_gaps_flagged_for_ofr">met|not_met</criterion>
  </criteria_report>
  <missing_inputs>
    <item>...</item>
  </missing_inputs>
  <blocking_issues>
    <issue>...</issue>
  </blocking_issues>
  <updated_asset>
    <!-- Complete QAL Asset Pack:
         Screening Rubric → S1–S6 → V1–V3 → Assets 1–5
         In this order. No sections omitted. -->
    ...
  </updated_asset>
</bbos_stage_output>
```

For Stage 01.1 REJ routing, set `<stage>01.1_REJ</stage>` and include Rejection Basis, Responsible Removal Log entry, and Operator-Facing Summary inside `<updated_asset>`.
