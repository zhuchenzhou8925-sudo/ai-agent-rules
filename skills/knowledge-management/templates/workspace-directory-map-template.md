# Workspace Directory Responsibility Map Template

| Area | Observed path | Role | Default access | Notes |
|---|---|---|---|---|
| Workbench | `<WORKBENCH_ROOT>` | Control rules, temporary outputs, active knowledge tools | Read first; write only to approved output areas | Keep formal vault boundaries explicit. |
| Rules repository | `<RULES_REPO>` | Source-controlled reusable rules and skills | Writable only when the user explicitly authorizes rule development or GitHub sync. | Do not commit private materials. |
| Legacy rules | `<LEGACY_RULES_DIR>` | Stable reference rules | Read-only | Do not modify during v1 work. |
| Knowledge base | `<KNOWLEDGE_BASE>` | Formal knowledge artifacts | Read-only during tests | Formal writes require user confirmation. |
| Source archive | `<SOURCE_ARCHIVE>` | Source materials and finalized original deliverables | Read-only until archive action is confirmed | Use `source_path` from knowledge artifacts. |

## Scan Notes

- Scope:
- Scan depth:
- Excluded areas:
- Key risks:
- Suggested next action:
