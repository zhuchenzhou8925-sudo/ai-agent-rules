---
name: obsidian-project-knowledge-skill
description: Use this skill when a user wants an AI assistant, Codex, ChatGPT project, or similar agent to organize project files, proposal materials, business documents, industry content, or report materials into a maintainable Obsidian knowledge base with project notes, resource indexes, MOCs, knowledge cards, links, tags, and document-output placeholders.
---

# Obsidian Project Knowledge Skill

## Purpose

This skill helps an AI assistant organize project-oriented materials into a maintainable Obsidian knowledge base.

Use it for:

- project files and project document packs;
- proposal, feasibility, solution, or report materials;
- business documents such as bidding, quotation, contract reference, and customer communication materials;
- industry content and scenario research;
- reusable knowledge extraction for future Word, PPT, Markdown, and report outputs.

This skill is a workflow template. It is not an Obsidian plugin, not a complete software product, and not a substitute for human review.

## Core rule

Start with the user's goal, then choose the workflow:

1. File organization.
2. File analysis.
3. Obsidian knowledge-base ingestion.
4. Project note or resource note generation.
5. Knowledge card generation.
6. MOC generation or MOC attachment.
7. Resource index generation.
8. Word / PPT / Markdown / report material preparation.

When local files are involved, always begin with read-only scanning. Do not move, delete, rename, overwrite, or archive original files unless the user explicitly confirms the action.

## Safety boundaries

- Only read user-authorized files and folders.
- Do not process private, confidential, or sensitive directories unless the user confirms access and redaction rules.
- Do not write into a formal Obsidian vault until the user confirms the destination.
- Do not treat drafts, logs, temporary files, or processing notes as formal knowledge.
- Do not invent facts that are not supported by source files.
- Mark uncertain, outdated, or unverified information clearly.
- Keep source references so the user can trace each note back to the original material.

## First-pass workflow

When the user gives a file or folder:

1. Confirm the task type and intended output.
2. Read-only scan the provided path.
3. Produce a file inventory with file type, likely topic, version clues, and possible duplicates.
4. Classify materials into:
   - project materials;
   - product capabilities;
   - industry scenarios;
   - business materials;
   - report materials;
   - reusable knowledge.
5. Recommend outputs:
   - project note or resource note;
   - resource index;
   - MOC;
   - knowledge cards;
   - document outline or report material.
6. Ask for confirmation before any write, migration, rename, deletion, or formal vault update.

User-provided materials should be treated as potentially useful. The main question is not "is this valuable?" but "how should this be organized, linked, and reused?"

## Obsidian output model

Use these artifact types:

- **Project note**: the main long-form note for a project, document pack, or topic.
- **Resource index**: a table or structured note listing source files, summaries, keywords, categories, and reuse directions.
- **Knowledge card**: a small atomic note focused on one reusable concept, method, claim, criterion, or expression.
- **MOC**: a map of content that links project notes, resource indexes, cards, related topics, and follow-up notes.

Do not replace the whole workflow with knowledge cards only. A complete ingestion usually needs project notes, indexes, MOCs, and links.

## Recommended note structure

Use the bundled templates when creating example outputs:

- `templates/project-note-template.md`
- `templates/knowledge-card-template.md`
- `templates/moc-template.md`
- `templates/image-placeholder-template.md`

For real user work, adapt the templates to the user's vault naming, tags, and folder structure.

## Image and diagram boundary

The assistant should not generate images, AI artwork, visual renders, cover images, architecture diagrams, or flowchart images directly.

For Word, PPT, Markdown, report, and solution outputs, only provide:

- image or diagram placeholders;
- usage position;
- expression purpose;
- core content elements;
- recommended layout;
- style requirements;
- AI image prompt for another image tool.

Use `templates/image-placeholder-template.md` for any architecture diagram, flowchart, cover visual, scene image, infographic, icon group, dashboard mockup, or prototype image.

## Suggested response pattern

For read-only scanning:

```markdown
## Scan Result
- Scope:
- File count:
- Main categories:
- Possible duplicates:
- Suggested outputs:
- Blockers:
- Next confirmation needed:
```

For draft generation:

```markdown
## Draft Output
- Created:
- Suggested vault location:
- Suggested MOC attachment:
- Source files:
- Needs human review:
- Next step:
```

For formal ingestion:

```markdown
## Ingestion Plan
- Files to ingest:
- Notes to create or update:
- MOCs to create or attach:
- Tags:
- Source traceability:
- Actions requiring confirmation:
```

## Human review checklist

Before finalizing or migrating any output:

- Are all source paths or source descriptions preserved?
- Are uncertain facts marked?
- Are private or sensitive details removed or approved?
- Are project facts separated from reusable conclusions?
- Are knowledge cards atomic?
- Does the MOC link to the right notes?
- Are drafts kept separate from reviewed vault content?
- Are image needs represented as placeholders rather than generated images?
