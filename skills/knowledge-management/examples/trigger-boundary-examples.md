# Trigger Boundary Examples

These examples help decide when to use `knowledge-management` and when another workflow should run first.

## Should Trigger

### Material Archiving Into The Knowledge Base

User: "Scan this material package and prepare a resource index, topic note plan, and knowledge-card suggestions for Obsidian filing."

Use `knowledge-management` because the primary goal is read-only scanning, material classification, source traceability, resource indexing, topic notes, and formal knowledge filing planning.

### Obsidian Knowledge Card Generation

User: "Extract reusable ideas from this solution material, generate Obsidian knowledge cards, and keep source_path."

Use `knowledge-management` because the output is reusable knowledge cards with source traceability for the Markdown knowledge base.

### MOC And Resource Index Organization

User: "Review this KnowledgeBase topic area and check whether MOCs, resource indexes, topic notes, and backlinks need updates."

Use `knowledge-management` because the task is local knowledge-base governance, MOC coverage, backlinks, and resource index organization.

## Should Not Trigger First

### Formal Bidding Analysis

User: "Analyze this tender file for scoring rules, rejection clauses, response requirements, and response risks."

Use `bidding-document-analysis` first because the primary goal is formal tender and response-risk analysis. Use `knowledge-management` later only if the user asks to preserve the analysis as reusable knowledge.

### One-Time PPT Or Word Drafting

User: "Use these materials to draft a presentation or Word report."

Do not prioritize `knowledge-management` if the user only wants a one-time deliverable. Use the relevant document-output workflow unless the user explicitly asks to file the result into the knowledge base.

## Boundary Example

### Business Materials Need Both Analysis And Filing

User: "These business materials need risk analysis and also need to become knowledge-base material."

Clarify the main goal and sequence first. If the immediate goal is risk or bid analysis, use the relevant business or bidding workflow first. Then use `knowledge-management` to create source-linked resource indexes, topic notes, knowledge cards, MOCs, backlinks, and tags.
