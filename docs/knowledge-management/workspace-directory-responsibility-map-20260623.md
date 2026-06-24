# Workspace Directory Responsibility Map - 2026-06-23

## Scan Boundary

- Analysis root: `<WORKSPACE_ROOT>`
- Scan depth: first-level and second-level directories only
- Scan mode: read-only
- Deep full-text scan: not performed
- Write target for this validation: `<RULES_REPO>`
- Formal KnowledgeBase writes: not performed

## Directory Responsibility Map

| Area | Observed path | Role | Default access for this work | Notes |
|---|---|---|---|---|
| Workspace root | `<WORKSPACE_ROOT>` | Analysis starting point | Read-only orientation | Not used as a free write location. |
| Workbench | `<WORKBENCH_ROOT>` | Codex control, active KnowledgeBase, old skills, temporary outputs, daily workbench | Read-only except explicitly approved output areas | This run does not write into this area. |
| Temporary AI outputs | `<AI_OUTPUT_DIR>` | Temporary handoff area for generated deliverables | Not used in this run | Plan requires test outputs to stay in the rules repository. |
| Codex control | `<CODEX_CONTROL_DIR>` | Existing control rules, logs, governance references | Read-only in this run | Not modified. |
| Formal knowledge base | `<KNOWLEDGE_BASE_DIR>` | Formal Obsidian / Markdown knowledge artifacts | Read-only in this run | No writes, including no writes to `_Codex_Output`. |
| Legacy skills | `<LEGACY_RULES_DIR>` | Existing skill and rule references | Read-only | Legacy Obsidian rules are the stable rollback reference. |
| Default draft output | `<CODEX_OUTPUT_DIR>` | Default draft, validation, and intermediate output area | Not used in this run | Validation is contained in the rules repository. |
| Historical vault output | `<KNOWLEDGE_BASE_DIR>/_Codex_Output` | Historical compatibility output area | Not used in this run | Not a default output target. |
| Active work | `<ACTIVE_WORK_DIR>` | Project materials and business context | Read-only orientation only | No deep read performed. |
| Knowledge and proposal archive | `<SOURCE_ARCHIVE>` | Source materials, finalized original deliverables, knowledge/proposal archive | Read-only orientation only | Formal archive actions require user confirmation. |
| Temporary area | `<TEMP_WORK_DIR>` | Short-lived local working area | Not used | Not part of v1 validation. |
| Templates | `<TEMPLATE_ASSET_DIR>` | Reusable templates and source assets | Read-only orientation only | No template content was copied. |
| Archive center | `<ARCHIVE_CENTER_DIR>` | Historical archive reference | Read-only orientation only | No deep read performed. |
| GitHub workspace | `<GITHUB_WORKSPACE>` | Local Git repositories | Scoped read/write by repository | Only authorized repositories are modified. |
| Rules repository | `<RULES_REPO>` | Source repository for reusable rules and skills | Writable for this plan | New skill, tests, reports, and docs are stored here. |
| Automation tools | `<AUTOMATION_TOOLS_REPO>` | Separate automation repository | Read-only orientation only | Not modified. |
| Digital workspace | `<DIGITAL_WORKSPACE_REPO>` | Separate workspace documentation repository | Read-only orientation only | Not modified. |
| Project sandbox | `<PROJECT_SANDBOX_REPO>` | Separate sandbox repository | Read-only orientation only | Not modified. |

## Responsibility Conclusions

- The rules source of truth for this change is `<RULES_REPO>`.
- The legacy rollback source is `<LEGACY_RULES_DIR>`.
- The formal knowledge base is intentionally outside the test output path.
- The source archive remains separate from formal knowledge artifacts.
- This scan is sufficient for v1 skill boundary design and does not justify deeper workspace-wide reading.
