---
name: knowledge-management
description: Use when the user's primary goal is workspace-level knowledge management for an Obsidian or Markdown knowledge base, including material archiving, formal knowledge filing, resource indexes, topic notes, MOCs, typed knowledge cards, backlinks, tags, frontmatter links, quality checks, and safe separation between source archives, temporary outputs, and formal knowledge outputs. Do not use it as the primary skill for formal bidding analysis or one-time document/PPT drafting unless the user explicitly wants knowledge-base filing.
---

# Knowledge Management Skill

## Purpose

This skill guides Codex through local Obsidian / Markdown knowledge-base work for the user workspace.

Use it when the user's goal is knowledge-base sedimentation, material archiving, Obsidian / Markdown knowledge organization, resource indexes, topic notes, MOCs, or knowledge cards.

Use it for:

- read-only analysis of a user's workspace structure when the output supports knowledge-base organization;
- project files, proposal materials, feasibility studies, research reports, literature, technical documents, product materials, policy standards, business documents, training or methodology materials, and reusable templates;
- recognizing material types before filing and choosing project, research, literature, technical, product, policy-standard, business, method, or future extension topic notes;
- organizing materials into resource indexes, multi-type topic notes, MOCs, typed knowledge cards, backlinks, frontmatter links, tags, formal filing locations, quality checks, and MOC attachment suggestions;
- keeping source archives, temporary outputs, and formal knowledge outputs separate.

This skill is a reusable runtime rule template. It is not an Obsidian plugin and does not directly run as a terminal command.

## Trigger Boundaries

Prioritize this skill only when the user asks to:

- file materials into an Obsidian / Markdown knowledge base;
- organize, classify, or archive materials for long-term knowledge reuse;
- create or update resource indexes, topic notes, MOCs, knowledge cards, backlinks, tags, or frontmatter links;
- review KnowledgeBase structure, duplicate topics, missing links, MOC coverage, or formal filing quality;
- convert analyzed materials into reusable knowledge artifacts after the source analysis is complete.

Do not prioritize this skill when:

- the primary goal is formal tender, bidding, procurement, scoring, response, or contract-risk analysis; use `bidding-document-analysis` first;
- the primary goal is a one-time Word, PPT, PDF, Excel, report, proposal, or presentation deliverable; use the relevant document-output workflow unless the user explicitly asks to file the result into the knowledge base;
- the primary goal is quotation calculation, legal advice, final bid production, external submission, or GitHub publishing.

For boundary cases, clarify the main goal first. If business or bidding materials need both analysis and knowledge filing, complete the domain analysis first, then use this skill to preserve source traceability, reusable judgments, topic notes, cards, MOCs, backlinks, and tags.

## Workspace Boundary

Use these placeholder paths when the user has authorized the relevant scope. Replace placeholders locally; do not commit real local paths to public repositories:

| Placeholder | Meaning |
|---|---|
| `<WORKSPACE_ROOT>` | Workbench root for control rules, temporary outputs, and the active knowledge base. |
| `<CODEX_CONTROL_DIR>` | Runtime control rules, directory map, and permanent error log. |
| `<CODEX_CONTROL_DIR>/ERROR_LOG.md` | Permanent error and blocker log. Read it before Obsidian / KnowledgeBase tasks. |
| `<OBSIDIAN_AGENT_RULES_DIR>` | Local Chinese Obsidian rule set. Read only the entry rule and directly relevant specialist rules. |
| `<KNOWLEDGE_BASE_DIR>` | Formal Obsidian / Markdown knowledge base. Write formal knowledge artifacts only after user authorization. |
| `<CODEX_OUTPUT_DIR>` | Temporary area only for tests, previews, exception reports, process checks, backups, or user-requested temporary outputs. |
| `<AI_OUTPUT_DIR>` | Temporary deliverable handoff area, not a long-term archive. |
| `<SOURCE_ARCHIVE>` | Source archive and finalized original deliverable archive. |
| `<RULES_REPO>` | GitHub sanitized rules repository. Do not modify during local Skill sync or ingestion tasks unless separately confirmed. |

## Legacy Compatibility

- `<KNOWLEDGE_BASE_DIR>/_Codex_Output` is historical compatibility only. Do not use it as the default output area.
- References to the legacy Obsidian workflow mean the local rule set under `<OBSIDIAN_AGENT_RULES_DIR>`, not a permission to restore old storage behavior.
- Keep local runtime rules and GitHub-safe sanitized rules separate. Do not copy placeholders or public-facing simplifications back into local runtime rules.
- When an old path or old filing habit conflicts with the current workspace boundary, follow the current boundary and report the compatibility issue.

## Core Safety Rules

- Begin local-file work with read-only scanning and inventory.
- Read `<CODEX_CONTROL_DIR>/ERROR_LOG.md` before Obsidian / KnowledgeBase tasks.
- Do not move, delete, rename, overwrite, or archive original files unless the user explicitly confirms that action.
- Do not write process files, validation records, check reports, backups, previews, exception reports, or other temporary outputs into the formal KnowledgeBase.
- Use `<CODEX_OUTPUT_DIR>` only for tests, previews, exception reports, process checks, backups, or user-requested temporary outputs when writes are approved.
- Keep the formal KnowledgeBase for user-authorized formal knowledge artifacts only.
- Keep source files and finalized original deliverables in `<SOURCE_ARCHIVE>` after user confirmation.
- Do not sync private vault content, customer materials, contracts, quotations, bidding files, run logs, secrets, tokens, keys, or unredacted business materials to GitHub.
- Keep local runtime rules and the GitHub sanitized copy separate. Do not copy sanitized placeholders into local runtime rules.
- GitHub repository changes must use a separate review branch, PR, and user confirmation. Codex must not merge by itself.
- Stop on blockers such as missing paths, unclear write scope, permission errors, suspected sensitive content, duplicate conflicts, target conflicts, or formal KnowledgeBase write requests without user authorization. Report the blocker instead of bypassing it.
- Pause for user confirmation before key write actions, including formal KnowledgeBase writes, overwrites, deletion, rename, archive actions, Git operations, or local Skill changes.
- Prefer existing tools, one-off commands, or inline commands for scanning, conversion, and checks. Do not write temporary scripts unless the user explicitly authorizes a durable script.
- Codex does not generate images for these workflows. For images, diagrams, Word, or PPT needs, provide text, structure, placeholders, purpose notes, and prompts for an image AI tool.
- Record validation limits honestly. If a dependency, parser, validator, or permission is unavailable, state the limitation and use a safer fallback rather than pretending the official validation passed.
- Mark uncertain, outdated, or unverified facts clearly.
- Preserve source traceability with `source` or `source_path` fields when creating knowledge artifacts.

## Task Routing

First identify the user's actual goal, then choose one route:

1. **File organization**: scan folders, inventory files, classify, and propose actions.
2. **File analysis for knowledge reuse**: summarize, compare versions, extract reusable points, and list gaps when the result will support knowledge filing.
3. **Knowledge-base filing**: prepare and formally file resource indexes, multi-type topic notes, MOCs, typed cards, links, and tags after user authorization.
4. **Document generation support**: prepare Markdown, Word, PPT, report, or proposal structures only when the document is part of knowledge-base sedimentation or filing.
5. **Business analysis support for filing**: extract reusable commercial boundaries and knowledge points after the proper domain analysis; use `bidding-document-analysis` first for formal bidding analysis.
6. **Local knowledge-base governance**: review structure, missing links, duplicate topics, and MOC coverage.
7. **Automation support**: use existing tools, one-off commands, or inline commands first; create persistent scripts only when repetitive, stable, and explicitly authorized.

For Obsidian formal knowledge filing, read the local entry rule first and then call specialist rules as needed:

- `Obsidian-智能归档入口规则.md`
- `knowledge-quality-standard.md`
- `material-type-decision-matrix.md`
- `topic-note-quality-standard.md`
- `knowledge-card-quality-standard.md`
- `quality-checklist.md`

## First-Pass Workflow

When the user provides a workspace, folder, or material set:

1. Confirm the task goal and output type from the prompt.
2. Scan only the authorized scope. For workspace-level orientation, scan first-level and second-level directories before any deeper read.
3. Produce a directory responsibility map or file inventory.
4. Identify material type before deciding the artifact shape:
   - primary material type;
   - secondary material type;
   - mixed-material relationship;
   - recommended topic note type;
   - whether knowledge cards are needed and which card types;
   - whether to create a new MOC, attach to an existing MOC, merge an existing note, or treat the input as a version update.
5. Recommend outputs:
   - resource index;
   - project, research, literature, technical, product, policy-standard, business, method, or extension topic note;
   - MOC;
   - typed knowledge cards;
   - backlinks and tags;
   - formal KnowledgeBase location suggestions;
   - upper-level MOC attachment suggestions.
6. Ask for confirmation before any write, formal KnowledgeBase filing, rename, deletion, or archive action.

If the user provides or authorizes materials for knowledge-base work, treat them as valuable by default. Do not repeatedly decide whether they are "worth filing"; decide how to perform high-quality formal knowledge filing.

Before formal knowledge filing, automatically check:

- primary and secondary material types;
- recommended topic note type;
- whether the topic should become a project, research, literature, technical, product, policy-standard, business, method, or extension note;
- whether knowledge cards are needed and which card types apply;
- whether the material is duplicate or should merge into an existing note/card;
- whether a same-topic topic note, project note, or resource note already exists;
- whether a related MOC already exists, a new MOC is needed, or an upper-level MOC should be updated;
- whether a resource index, topic note, knowledge card set, or combination is needed;
- whether backlinks and frontmatter `links` need updates;
- whether the formal output should merge, de-duplicate, link to existing knowledge, or attach to an upper-level MOC;
- which KnowledgeBase area is most likely correct. If the user has not named an area, infer it and explain the reason instead of requiring the user to classify it first.

Do not create numbered depth tiers. Authorized materials should receive deep analysis by default. Do not default to temporary output or pre-filing holding status. If source scope, write authorization, target location, conflicts, sensitive boundaries, or readability are unclear, stop and report a blocker instead of filing.

Formal knowledge outputs should include business understanding, structural analysis, mechanism breakdown, applicable boundaries, related knowledge links, and reusable wording. Validation must check knowledge quality, not only frontmatter, tags, and backlinks. Specifically check for shallow summaries, raw material stacking, concept excerpts, weak business reuse value, missing mechanism breakdown, unclear boundaries, and missing related-knowledge links.

The formal filing flow is:

1. Read control rules.
2. Identify material type with `material-type-decision-matrix.md`.
3. Choose the topic note type with `topic-note-quality-standard.md`.
4. Decide whether to generate knowledge cards and card types with `knowledge-card-quality-standard.md`.
5. Decide MOC creation or attachment.
6. Decide merge, de-duplication, and version update handling.
7. Generate formal knowledge artifacts after authorization.
8. Run the unified quality check in `quality-checklist.md`.
9. Output a concise confirmation report.

## Output Model

Use the same knowledge artifact types as the legacy Obsidian workflow:

- **Resource index**: source list, categories, keywords, material/version relationships, core judgments, business insights, applicable boundaries, reuse directions, and follow-up knowledge directions.
- **Topic note**: long-form analytical note chosen by material type, including project, research, literature, technical, product, policy-standard, business, method, and future extension notes.
- **Topic note variants**: project, research, literature, technical, product, policy-standard, business, method, extension, or source-specific analytical notes. Do not force all materials into project notes.
- **Knowledge card**: typed atomic reusable judgment, method, model, scenario, requirement, risk, expression, comparison, or case insight with business value.
- **MOC**: map of content linking topic notes, project notes, resource indexes, knowledge cards, related topics, and follow-up items.
- **Formal filing suggestion**: proposed KnowledgeBase target location, prerequisites, risks, and items requiring user confirmation.
- **Upper-level MOC attachment suggestion**: where a new artifact should be linked in the knowledge structure.

Do not replace the workflow with knowledge cards only. A complete filing closure must at least check the material type decision, topic note type, resource index, topic note necessity, knowledge card necessity and card type, MOC attachment, related links, frontmatter, formal KnowledgeBase write authorization, unified quality checklist, and final review report.

Use the current KnowledgeBase naming habit under `<KNOWLEDGE_BASE_DIR>/<DOMAIN_AREA>`:

- `主题名称-MOC-YYYYMMDD.md`
- `知识点名称-知识卡片-YYYYMMDD.md`
- `主题名称-资料索引-YYYYMMDD.md`
- `项目名称-项目笔记-YYYYMMDD.md`
- `主题名称-研究笔记-YYYYMMDD.md`
- `文献主题-文献笔记-YYYYMMDD.md`
- `技术对象-技术笔记-YYYYMMDD.md`
- `产品名称-产品笔记-YYYYMMDD.md`
- `政策或标准名称-政策标准笔记-YYYYMMDD.md`
- `商务事项-商务笔记-YYYYMMDD.md`
- `方法名称-方法笔记-YYYYMMDD.md`
- `主题名称-扩展笔记-YYYYMMDD.md`
- `主题名称-资料笔记-YYYYMMDD.md`

Use `created: YYYY-MM-DD` in frontmatter.

## Storage Continuity

Keep these storage roles separate:

- Tests, previews, exception reports, process checks, backups, and explicit user-requested temporary outputs stay in `<CODEX_OUTPUT_DIR>` when writes are approved; validation work belongs under process checks and is not a separate temporary-output category.
- Original source materials and finalized original deliverables belong in `<SOURCE_ARCHIVE>` after user confirmation.
- The formal KnowledgeBase keeps only user-authorized formal knowledge artifacts such as MOCs, resource indexes, multi-type topic notes, project notes, resource notes, and knowledge cards.
- `<AI_OUTPUT_DIR>` is only a temporary deliverable handoff area, not a formal archive and not a KnowledgeBase.

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

For formal knowledge filing planning:

```markdown
## Knowledge Filing Plan
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
- `<CODEX_CONTROL_DIR>/ERROR_LOG.md` was read for Obsidian / KnowledgeBase work.
- Formal KnowledgeBase files were not modified before user authorization.
- Output locations matched the user's boundary rules.
- Source references were preserved.
- Private or sensitive details were removed, parameterized, or explicitly approved.
- Process checks, logs, validation records, previews, exception reports, and temporary outputs were kept out of the formal knowledge base.
- Formal knowledge artifacts contain business understanding, structural analysis, mechanism breakdown, applicable boundaries, related knowledge links, and reusable wording where relevant.
- Formal filing used material type recognition rather than forcing every input into a project note.
- Topic notes and knowledge cards follow the relevant quality standards and type-specific minimum requirements.
- Validation checked for shallow summaries, raw material stacking, concept excerpts, weak business reuse value, missing mechanism breakdown, unclear boundaries, and missing related-knowledge links.
- Sensitive information checks were performed before any GitHub-oriented handoff.
- Any blocker, missing dependency, or validation limitation was reported clearly.
- The result states whether it is a test, preview, validation record, exception report, formal filing suggestion, or formal knowledge artifact.

- GitHub repositories, source materials, AI output deliverables, and unrelated workspace files were not modified.
