# Legacy Capability Coverage Matrix - 2026-06-23

## Scope

This matrix checks whether `skills/knowledge-management/SKILL.md` preserves the old Obsidian knowledge workflow capabilities while adding workspace-level safety boundaries.

Legacy reference directory:

```text
/Users/zoezhu/工作区/00_工作台/Skills/Obsidian知识库
```

The legacy directory is read-only for this validation.

## Coverage Matrix

| Capability | Legacy reference | v1 support | Evidence in v1 | Gap / action |
|---|---|---|---|---|
| Goal-first routing | 知识库总规则, 智能归档入口规则 | Covered | `Task Routing`, `First-Pass Workflow` | No gap. |
| Read-only scan before local file work | 知识库总规则, 智能归档入口规则, 测试用例与验收规则 | Covered | `Core Safety Rules`, `First-Pass Workflow` | No gap. |
| Workspace-level shallow analysis | New v1 requirement | Covered | `Workspace Boundary`, `First-Pass Workflow` | No gap. |
| Six material categories | 文件命名与分类规则, 资料组知识化处理流程 | Covered | `First-Pass Workflow` category list | No gap. |
| Resource index | 资料索引生成规则 | Covered | `Output Model` | No gap. |
| Project note / resource note | 项目笔记生成规则, 资料组知识化处理流程 | Covered | `Output Model` | No gap. |
| MOC | MOC生成规则 | Covered | `Output Model` | No gap. |
| Knowledge card | 知识卡片生成规则 | Covered | `Output Model` | No gap. |
| Backlinks and tags | MOC生成规则, 知识库总规则 | Covered | `Output Model`, `Review Checklist` | No gap. |
| Migration suggestion | 智能归档入口规则 | Covered | `Output Model`, `First-Pass Workflow` | No gap. |
| Upper-level MOC attachment suggestion | MOC生成规则, 智能归档入口规则 | Covered | `Output Model`, `Suggested Response Pattern` | No gap. |
| Source traceability | 知识库总规则, 资料索引生成规则 | Covered | `Core Safety Rules`, `Storage Continuity`, `Review Checklist` | No gap. |
| No formal KnowledgeBase writes during tests | New v1 requirement plus legacy safety boundary | Covered | `Core Safety Rules`, `Storage Continuity` | No gap. |
| Separation of draft, source archive, and formal knowledge outputs | 知识库总规则, 智能归档入口规则 | Covered | `Storage Continuity` | No gap. |
| GitHub-safe publication boundary | Existing repository safety rules | Covered | `Core Safety Rules`, `Workspace Boundary` | No gap. |
| Automation support | Codex工作区执行总规则 style behavior | Covered at workflow level | `Task Routing` route 7 | No script added in v1 because current need is documentation and validation. |
| Rollback to legacy rules | User plan requirement | Covered by repository docs and evaluation report | `Evaluation report`, `setup guide update` | No gap after documentation update. |

## Conclusion

The v1 skill covers the old Obsidian workflow entry points, artifacts, safety boundaries, and rollback expectations. It adds a workspace-level scan boundary and a stronger test-output rule: validation materials stay in the rules repository and do not enter the formal KnowledgeBase.
