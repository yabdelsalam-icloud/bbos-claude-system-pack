# BBOS Operator Onboarding Guide
@@DOC:BBOS_OPERATOR_ONBOARDING@@

**For:** Operators setting up BBOS on Claude for the first time.
**Time required:** 15–20 minutes to read. Your first session will take as long as your intake takes to complete.

---

## What you are setting up

BBOS on Claude is a structured AI operating system that guides your business through eight stages — from honest self-assessment through offer, outreach, sales, fulfillment, retention, and optimization. Claude acts as a team of specialists, each bounded to their role. A governor oversees the routing. Validators check the work before anything advances.

The system is designed to prevent the most common failure mode: building on a foundation that is not actually true.

---

## Before your first session

You need three things ready before you open Claude:

**1. Your intake answers** — honest responses to the six intake sections:
- **Capital:** What is your actual financial runway? Not the optimistic version. The number that is true.
- **Skills:** What is your core competency? What do you have verifiable evidence for?
- **Proof:** Links or references that substantiate your claimed skills and results.
- **Constraints:** What are your 3–5 non-negotiable work aversions? What are your real limits on time, capital, and capacity?
- **Geography:** Where specifically will you operate? What zoning or community context applies?
- **Regulatory:** What permits, licenses, or compliance requirements apply to your intended work?

You do not need to answer in any special format. Answer honestly in plain language. Claude will normalise and gap-check.

**2. A folder for your project files** — you will be saving asset packs and a state file as you progress through stages. Create a folder now. Name it clearly.

**3. A copy of the `state.json` template** — paste this into a new file in your project folder and save it as `state.json`:

```json
{
  "schema_version": "2.0",
  "project_id": "your-project-name",
  "active_stage": "00_INT",
  "active_command": "INTAKE",
  "routing_status": "remain",
  "last_validated_at": "",
  "required_inputs": [],
  "required_validators": [],
  "blocking_issues": [],
  "artifacts": {
    "stage_00_intake_packet": null,
    "stage_00.1_form_mapping_guide": null,
    "stage_01_qal_asset_pack": null,
    "stage_02_str_asset_pack": null,
    "stage_03_ofr_asset_pack": null,
    "stage_04_out_asset_pack": null,
    "stage_05_sal_asset_pack": null,
    "stage_06_ful_asset_pack": null,
    "stage_07_ret_asset_pack": null,
    "stage_08_opt_asset_pack": null
  },
  "notes": []
}
```

Replace `"your-project-name"` with a short identifier for your business or project.

---

## Your first session — step by step

### Step 1: Open Claude and paste your opening message

Your first message should follow this format exactly:

```
[Project state — new project]
Active stage: 00_INT
Active command: INTAKE
Routing status: remain

[Intake answers]

Capital: [your honest answer]
Skills: [your honest answer]
Proof: [your links or references]
Constraints: [your honest answer]
Geography: [your honest answer]
Regulatory: [your honest answer]

INTAKE
```

The word `INTAKE` at the end is the command. Claude will process your answers, normalise them, run the gap check, and issue a routing decision.

### Step 2: Read the gap check carefully

Claude will return a Normalised Intake Packet and a Gap Check. The gap check lists anything missing, ambiguous, or unverifiable. This is not criticism — it is the system doing its job. A gap here prevents a larger problem later.

If gaps are listed, answer them. Paste your answers and send another `INTAKE` message. Claude will re-run the gap check.

### Step 3: Receive the routing decision

Once the gap check clears, Claude will issue a Routing Decision: either `proceed to Stage 01 QAL` or `NO-SHIP — INTAKE INCOMPLETE` with specific items listed.

If you receive `proceed`, the intake is complete. If you receive NO-SHIP, more information is needed before the system can route you forward.

### Step 4: Save your outputs

Copy Claude's Normalised Intake Packet output into a new file. Save it as `00_intake_packet_v1.md` in your project folder.

Update your `state.json`:
- Change `routing_status` to `advance`
- Update `artifacts.stage_00_intake_packet` to the file path
- Add a notes entry with today's date

### Step 5: Begin Stage 01 QAL in your next session

Follow the Session Re-Entry Protocol (`docs/operator_session_reentry.md`) to open Stage 01 correctly.

---

## Commands you will use (quick reference)

| Command | What it does |
|---|---|
| `INTAKE` | Captures, normalises, and routes intake data |
| `S-OUTPUTS` | Runs the Research Factory for the active stage |
| `ASSEMBLE` | Builds the complete asset pack for the active stage |
| `PATCH [section name]` | Revises one named section without touching the rest |
| `ANNOTATE` | Adds spiritual annotations (explicit invocation only) |
| `RESET ROUTING` | Drops inferred context, re-anchors to a named stage |

---

## What the governor does (and does not do)

The governor routes commands, enforces stage isolation, and recommends whether to remain, advance, patch, or no_ship. It does not generate content itself. It does not advance the stage automatically — you update `state.json` after each session based on the governor's recommendation.

Think of the governor as the gatekeeper and the stage skills as the specialists. The governor decides who works. The specialists do the work.

---

## A note on pacing

The system is designed to go slowly on purpose. The intake and qualification stages exist to prevent you from building a sophisticated offer on top of an unclear foundation. Operators who rush through Stage 00 and 01 consistently encounter structural problems at Stage 03 and beyond that require going back.

The gap check is the system's most important output. If it finds gaps, close them before moving forward.

---

## Getting help

If Claude returns a `no_ship` recommendation and you are not sure what is needed, ask:

```
RESET ROUTING
Active stage: [current stage]
What specifically is preventing me from advancing?
```

Claude will list the blocking items with resolution paths.

---

*This guide covers first-session onboarding only. For ongoing session management, see `docs/operator_session_reentry.md`. For the full stage map and progression rules, see `docs/master_stage_map.md`.*
