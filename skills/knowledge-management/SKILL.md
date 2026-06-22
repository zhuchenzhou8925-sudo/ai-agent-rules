---
name: knowledge-management
description: Use this skill when a user wants workspace-level knowledge management for an Obsidian or Markdown knowledge base, including read-only folder analysis, material classification, project notes, resource indexes, MOCs, knowledge cards, backlinks, tags, migration suggestions, and safe handoff between source archives and formal knowledge outputs.
---

# Knowledge Management Skill

## Purpose

This skill guides an AI assistant through workspace-level knowledge management for an Obsidian or Markdown vault.

Use it for:

- read-only analysis of a user's workspace structure;
- project files, proposal materials, feasibility studies, reports, business documents, and reusable templates;
- organizing materials into resource indexes, project notes, resource notes, MOCs, knowledge cards, backlinks, tags, and migration suggestions;
- keeping source archives, temporary outputs, and formal knowledge outputs separate.

Version v1 supports only Obsidian / Markdown / backlink / MOC workflows. It is not an Obsidian plugin and does not directly run as a terminal command.

## Workspace Boundary

Start from the user-approved workspace root, normally represented as:

```text
<WORKSPACE_ROOT>
```

Use these logical locations:

| Variable | Meaning |
|---|---|
| `<WORKBENCH_ROOT>` | Workbench area for control rules, temporary outputs, and the active knowledge base. |
| `<RULES_REPO>` | Git-managed source repository for reusable rules and skills. |
| `<LEGACY_RULES_DIR>` | Existing stable legacy rules. Read-only reference only. |
| `<KNOWLEDGE_BASE>` | Formal Obsidian or Markdown knowledge base. Do not write during tests. |
| `<CODEX_OUTPUT_DIR>` | Temporary draft and validation output area when the user allows workspace writes. |
| `<SOURCE_ARCHIVE>` | Source material and finalized original deliverable archive. |

For public rule repositories, prefer placeholders such as `<WORKSPACE_ROOT>` and `<KNOWLEDGE_BASE>`. Local absolute paths may appear only in local validation reports when needed to prove what was tested.

## Core Safety Rules

- Begin local-file work with read-only scanning.
- Do not move, delete, rename, overwrite, or archive original files unless the user explicitly confirms that action.
- Do not modify legacy rules while creating or testing this skill.
- Do not write to the formal knowledge base during skill tests, including any `_Codex_Output` folder inside the formal vault.
- Do not sync private vault content, customer materials, contracts, quotations, bidding files, run logs, secrets, tokens, keys, or unredacted business materials to GitHub.
- Stop on blockers such as missing paths, unclear write scope, permission errors, suspected sensitive content, duplicate conflicts, or formal-ingestion requests without user confirmation. Report the blocker instead of bypassing it.
- Record validation limits honestly. If a dependency, parser, validator, or permission is unavailable, state the limitation and use a safer fallback rather than pretending the official validation passed.
- Mark uncertain, outdated, or unverified facts clearly.
- Preserve source traceability with `source` or `source_path` fields when creating knowledge artifacts.

## Task Routing

First identify the user's actual goal, then choose one route:

1. **File organization**: scan folders, inventory files, classify, and propose actions.
2. **File analysis**: summarize, compare versions, extract reusable points, and list gaps.
3. **Knowledge-base ingestion**: prepare resource indexes, project notes, resource notes, MOCs, cards, links, and tags.
4. **Document generation support**: prepare Markdown, Word, PPT, report, or proposal structures from validated materials.
5. **Business analysis support**: analyze contracts, quotations, bidding materials, and commercial boundaries after authorization.
6. **Local knowledge-base governance**: review structure, missing links, duplicate topics, and MOC coverage.
7. **Automation support**: create scripts only when repetitive scanning, conversion, table generation, or validation needs deterministic handling.

## First-Pass Workflow

When the user provides a workspace, folder, or material set:

1. Confirm the task goal and output type from the prompt.
2. Scan only the authorized scope. For workspace-level orientation, scan first-level and second-level directories before any deeper read.
3. Produce a directory responsibility map or file inventory.
4. Classify materials into:
   - project materials;
   - product capabilities;
   - industry scenarios;
   - business materials;
   - report materials;
   - reusable knowledge.
5. Recommend outputs:
   - resource index;
   - project note or resource note;
   - MOC;
   - knowledge cards;
   - backlinks and tags;
   - migration suggestions;
   - upper-level MOC attachment suggestions.
6. Ask for confirmation before any write, formal ingestion, migration, rename, deletion, or archive action.

## Output Model

Use the same knowledge artifact types as the legacy Obsidian workflow:

- **Resource index**: source list, summaries, categories, keywords, reuse directions, and processing status.
- **Project note / resource note**: long-form note for a project, topic, or document pack.
- **Knowledge card**: atomic reusable concept, method, claim, criterion, expression, or case insight.
- **MOC**: map of content linking project notes, resource indexes, knowledge cards, related topics, and follow-up items.
- **Migration suggestion**: proposed target location, prerequisites, risks, and items requiring user confirmation.
- **Upper-level MOC attachment suggestion**: where a new artifact should be linked in the knowledge structure.

Do not replace the workflow with knowledge cards only. A usable ingestion normally needs indexes, notes, MOCs, links, and review status.

## Storage Continuity

Keep these storage roles separate:

- Temporary AI-generated deliverables or validation outputs stay in the user's approved temporary output area or the rules repository test documentation area.
- Original source materials and finalized original deliverables belong in the source archive after user confirmation.
- The formal knowledge base keeps only user-confirmed knowledge artifacts such as MOCs, resource indexes, project notes, resource notes, and knowledge cards.

During this skill's own development and validation, write all test outputs, matrices, validation records, and evaluation reports into the rules repository, not into the formal knowledge base.

## Suggested Response Pattern

For workspace scanning:

```markdown
## Workspace Scan Result
- Scope:
- Scan depth:
- Core areas:
- Output boundary:
- Risks:
- Suggested next action:
```

For ingestion planning:

```markdown
## Knowledge Ingestion Plan
- Source materials:
- Artifacts to create:
- Suggested vault location:
- Source traceability:
- MOC attachment:
- Confirmation required:
```

For validation:

```markdown
## Validation Result
- Legacy coverage:
- Safety boundary:
- Output location:
- Sensitive information check:
- Recommendation:
```

## Review Checklist

Before presenting a result as ready:

- Source scope was authorized and not expanded silently.
- Workspace scans were shallow unless deeper reading was necessary and justified.
- Legacy rules and formal knowledge base files were not modified during tests.
- Output locations matched the user's boundary rules.
- Source references were preserved.
- Private or sensitive details were removed, parameterized, or explicitly approved.
- Drafts, logs, validation records, and temporary outputs were kept out of the formal knowledge base.
- Sensitive information checks were performed before any GitHub-oriented handoff.
- Any blocker, missing dependency, or validation limitation was reported clearly.
- The result states whether it is a draft, validation record, migration suggestion, or formal knowledge artifact.

## Validation References

When testing or changing this skill inside the rules repository, use the repository validation materials as the audit trail:

- `docs/knowledge-management/legacy-capability-coverage-matrix-20260623.md`
- `docs/knowledge-management/workspace-directory-responsibility-map-20260623.md`
- `docs/reports/knowledge-management-skill-v1-evaluation-20260623.md`

Use these files to confirm legacy capability coverage, workspace write boundaries, and whether the current version is ready for PR review. Test reports belong in the rules repository test or report directories, not in the formal knowledge base.
