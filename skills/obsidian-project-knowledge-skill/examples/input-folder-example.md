# Example: Input Folder Scan

This example shows the expected first response when a user provides a folder of project materials.

## User request

```text
Please organize this project folder into my Obsidian knowledge base:

project-materials/
```

## Expected assistant behavior

The assistant should not move, delete, rename, or archive anything during the first pass. It should scan the folder read-only and return an inventory and organization plan.

## Example output

```markdown
## Scan Result

- Scope: `project-materials/`
- Mode: read-only scan
- File count: 18
- Main categories:
  - Project materials: project brief, meeting notes, delivery plan
  - Product capabilities: platform module overview, integration notes
  - Industry scenarios: industry background and benchmark case notes
  - Business materials: quotation assumptions and contract reference notes
  - Report materials: presentation draft and leadership summary
  - Reusable knowledge: delivery methodology and risk-control checklist

## Suggested Outputs

1. Project note:
   - `Example Project - Project Note`
   - Purpose: preserve project context, objectives, scope, delivery path, and risks.

2. Resource index:
   - `Example Project - Resource Index`
   - Purpose: list all source files, categories, summaries, keywords, and reuse directions.

3. MOC:
   - `Example Project MOC`
   - Purpose: connect the project note, resource index, and future knowledge cards.

4. Knowledge cards:
   - Delivery risk-control method
   - Platform integration checklist
   - Project reporting structure

## Confirmation Needed

Please confirm whether I should create draft Markdown notes first. I will not migrate them into the formal Obsidian vault until you confirm the target location.
```

## Notes

The assistant should treat the user's materials as potentially useful and decide how to organize them. Low-value, duplicate, or unclear files can be flagged, but should not be deleted or ignored without user confirmation.
