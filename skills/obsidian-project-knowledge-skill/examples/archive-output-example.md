# Example: Obsidian Ingestion Output

This example shows a concise draft ingestion report after the user has approved draft note generation.

## Example output

```markdown
## Draft Output

- Created:
  - `Example Project - Resource Index.md`
  - `Example Project - Project Note.md`
  - `Example Project MOC.md`
  - `Delivery Risk-Control Method - Knowledge Card.md`
  - `Platform Integration Checklist - Knowledge Card.md`

- Suggested vault location:
  - Project note: `01_项目资料/项目笔记/`
  - Resource index: `08_资料索引/项目资料索引/`
  - MOC: `07_MOC/项目MOC/`
  - Knowledge cards: `06_可复用知识/知识卡片/`

- Suggested MOC attachment:
  - Attach `Example Project MOC` to the relevant industry or topic MOC.

- Source files:
  - All draft notes include source file names and source descriptions.
  - Formal source paths should be verified before migration.

- Needs human review:
  - Confirm final vault locations.
  - Confirm whether business assumptions are approved.
  - Confirm whether any customer-specific content should be redacted.

- Next step:
  - If approved, migrate drafts to the formal vault and mark them reviewed.
```

## Expected qualities

- Drafts and formal reviewed notes are kept separate.
- Project facts are not generalized into universal claims without review.
- Knowledge cards are small and focused.
- MOC links are proposed, not silently forced into the vault.
- Human confirmation is required before formal migration.
