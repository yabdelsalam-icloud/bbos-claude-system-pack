# BBOS State Schema v2
@@DOC:BBOS_STATE_SCHEMA_V2@@

**Replaces:** `runtime/state_schema.json` (v1 — unstructured artifacts object, untyped notes array)

---

## Full schema definition

```json
{
  "schema_version": "2.0",
  "project_id": "string — unique identifier for this project",
  "active_stage": "one of: 00_INT | 00.1_IFB | 01_QAL | 01.1_REJ | 02_STR | 02.1_STRESS | 03_OFR | 04_OUT | 05_SAL | 05.1_DQ | 06_FUL | 07_RET | 08_OPT",
  "active_command": "one of: INTAKE | S-OUTPUTS | ASSEMBLE | ANNOTATE | PATCH | RESET ROUTING",
  "routing_status": "one of: remain | advance | patch | no_ship",
  "last_validated_at": "YYYY-MM-DD",
  "required_inputs": ["string — plain language description of each missing required input"],
  "required_validators": ["string — validator skill names required before ADVANCE for the active stage"],
  "blocking_issues": [
    {
      "issue": "string — plain language description",
      "linked_asset": "string — asset name or null",
      "linked_validator": "string — validator that flagged this, or null",
      "resolution_path": "string — what action resolves this issue"
    }
  ],
  "artifacts": {
    "stage_00_intake_packet": "path/to/file or null",
    "stage_00.1_form_mapping_guide": "path/to/file or null",
    "stage_01_qal_asset_pack": "path/to/file or null",
    "stage_02_str_asset_pack": "path/to/file or null",
    "stage_03_ofr_asset_pack": "path/to/file or null",
    "stage_04_out_asset_pack": "path/to/file or null",
    "stage_05_sal_asset_pack": "path/to/file or null",
    "stage_06_ful_asset_pack": "path/to/file or null",
    "stage_07_ret_asset_pack": "path/to/file or null",
    "stage_08_opt_asset_pack": "path/to/file or null"
  },
  "notes": [
    {
      "timestamp": "YYYY-MM-DD",
      "author": "one of: operator | system",
      "linked_asset": "artifact key from artifacts object, or null",
      "note": "string — brief description of what changed, was decided, or needs attention"
    }
  ]
}
```

---

## Artifact key rules

- Keys are fixed and canonical. Do not invent new artifact keys.
- Each key maps to exactly one file path (or `null` if not yet produced).
- File paths are relative to the project root.
- When a new version of an asset pack is produced, update the path to the new version. Previous versions are retained in the file system but the state object always points to the current working version.
- The governor reads artifact presence from this object when checking required inputs. If a key is `null`, the corresponding asset is considered absent.

---

## State integrity rules (operator responsibility)

Before closing any session, verify:

1. `active_stage` matches the stage you actually worked in.
2. `routing_status` matches the governor's last recommendation for that session.
3. `blocking_issues` is accurate — resolved issues removed, new issues added with `resolution_path`.
4. The artifact key for the active stage points to the current file version.
5. At least one `notes` entry has been added describing what happened in the session.

**Logically invalid states to avoid:**

| Invalid combination | Why it is invalid |
|---|---|
| `routing_status: advance` + non-empty `blocking_issues` | Cannot advance with unresolved blocks |
| `routing_status: no_ship` + empty `required_inputs` and empty `blocking_issues` | No_ship requires a stated reason |
| `active_stage: 03_OFR` + `artifacts.stage_02_str_asset_pack: null` | OFR cannot begin without STR inputs |

---

## Example populated state (Stage 03 OFR, mid-session)

```json
{
  "schema_version": "2.0",
  "project_id": "tranquility-journey-2026",
  "active_stage": "03_OFR",
  "active_command": "PATCH",
  "routing_status": "patch",
  "last_validated_at": "2026-03-12",
  "required_inputs": [],
  "required_validators": [
    "bbos-glabel-auditor",
    "bbos-truth-gate-validator",
    "bbos-stage-completeness-checker"
  ],
  "blocking_issues": [
    {
      "issue": "Guarantee missing Operator-Side Boundaries element",
      "linked_asset": "stage_03_ofr_asset_pack",
      "linked_validator": "bbos-stage-completeness-checker",
      "resolution_path": "PATCH Asset 6 — Guarantee to add explicit operator-side boundaries clause"
    }
  ],
  "artifacts": {
    "stage_00_intake_packet": "working_assets/00_intake_packet_v1.md",
    "stage_00.1_form_mapping_guide": null,
    "stage_01_qal_asset_pack": "working_assets/01_qal_asset_pack_v1.md",
    "stage_02_str_asset_pack": "working_assets/02_str_asset_pack_v1.md",
    "stage_03_ofr_asset_pack": "working_assets/03_ofr_asset_pack_v0_2.md",
    "stage_04_out_asset_pack": null,
    "stage_05_sal_asset_pack": null,
    "stage_06_ful_asset_pack": null,
    "stage_07_ret_asset_pack": null,
    "stage_08_opt_asset_pack": null
  },
  "notes": [
    {
      "timestamp": "2026-03-11",
      "author": "operator",
      "linked_asset": "stage_03_ofr_asset_pack",
      "note": "First ASSEMBLE pass complete. Glabel-auditor passed. Truth-gate passed. Completeness checker failed on Asset 6 guarantee missing operator-side boundaries."
    },
    {
      "timestamp": "2026-03-12",
      "author": "operator",
      "linked_asset": "stage_03_ofr_asset_pack",
      "note": "Began PATCH session for Asset 6. Boundaries clause drafted but needs pricing team confirmation before validator re-run."
    }
  ]
}
```

---

*Schema version 2.0 supersedes the unstructured v1 schema. Existing projects using v1 should migrate artifacts to the canonical key names and convert notes to the typed format before next session.*
