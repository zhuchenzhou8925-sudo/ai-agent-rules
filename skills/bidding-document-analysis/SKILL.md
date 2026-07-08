---
name: bidding-document-analysis
description: 用于分析招标文件、采购文件、评分办法、合同条款、响应要求和投标风险，并形成结构化投标分析与响应框架建议。
---

# Bidding Document Analysis

## Purpose

Use this skill to analyze bidding, tender, procurement, scoring, contract, delivery, and response requirements from authorized bid-related materials.

The first version only supports bidding document analysis, scoring-item extraction, response-requirement decomposition, contract-risk identification, delivery-requirement extraction, and response-framework suggestions.

Do not use it to generate a formal final bid document, promise win probability, provide legal opinions, perform automatic quotation calculation, modify source files, or publish to GitHub.

## Trigger Conditions

Use this skill when the user asks to:

- analyze tender documents, bidding documents, procurement files, or request-for-proposal materials;
- extract scoring items, evaluation criteria, qualification requirements, substantial response requirements, or rejection clauses;
- analyze procurement needs, delivery requirements, service scope, project schedule, or acceptance requirements;
- identify contract risks in bid-related contract terms;
- build a response-file framework based on procurement requirements and scoring criteria;
- list missing materials, response risks, and questions requiring user confirmation;
- prepare structured analysis before deciding whether or how to respond to a bid.

## Applicable Scenarios

- Tender or procurement document analysis.
- Procurement requirement decomposition.
- Scoring method and evaluation criteria extraction.
- Qualification and substantial response requirement identification.
- Rejection-clause and bid-invalidity risk identification.
- Contract clause risk analysis for bid response.
- Delivery requirement and acceptance requirement extraction.
- Response-file framework suggestion.
- Missing-material and question-list preparation.
- Internal bid-response preparation and review support.

## Non-Applicable Scenarios

Do not use this skill for:

- generating a formal final bid document without further confirmation;
- automatic quotation calculation or pricing commitment;
- win-probability commitment or bid-winning promise;
- legal opinion or lawyer-substitute contract advice;
- automatic seal, signature, submission, or external delivery of bid documents;
- modifying, moving, deleting, renaming, overwriting, or archiving original files;
- complete software system development;
- frontend, backend, database, MCP, plugin, deployment, or operations design;
- automatic GitHub sync, push, pull request, merge, or release.

If the request drifts into any non-applicable scenario, stop and clarify the allowed analysis scope.

## Input File Types

Common input materials include:

- tender announcement;
- bidding document, tender document, procurement document, or RFP;
- procurement requirement statement;
- scoring method, evaluation criteria, or bid evaluation rules;
- bidder instructions;
- qualification requirements;
- substantial response requirements;
- rejection clauses or bid-invalidity terms;
- contract template or contract terms;
- technical specification;
- business terms;
- delivery and acceptance requirements;
- company qualification, case, product, or service-capability materials;
- historical bid-response templates.

## Output Types

Produce structured outputs such as:

- tender document structure summary;
- project basic information summary;
- procurement requirement decomposition table;
- qualification requirement checklist;
- substantial response requirement checklist;
- rejection-clause and bid-invalidity risk list;
- scoring item extraction table;
- contract clause risk list;
- delivery and acceptance requirement checklist;
- response-file framework suggestion;
- missing-material checklist;
- questions requiring user confirmation;
- bid-response risk summary;
- recommended next steps.

Clearly label uncertainty, inference, missing source material, and items requiring manual review.

## Standard Execution Flow

1. Confirm the analysis goal: bid/no-bid decision support, response framework, scoring strategy, risk review, or material preparation.
2. Confirm the authorized reading scope, especially before reading large batches of files.
3. Confirm sensitive-material boundaries if files involve quotation, customer, contract, qualification, supplier, project strategy, or other confidential content.
4. Read only authorized materials and keep source files unchanged.
5. Build a file inventory and document/chapter structure summary.
6. Extract project basic information: purchaser, project name, procurement scope, timeline, submission requirements, delivery requirements, and acceptance requirements.
7. Extract qualification requirements, substantial response requirements, and rejection clauses.
8. Decompose scoring criteria into business, technical, price, subjective, objective, evidence, and documentation requirements where applicable.
9. Analyze contract terms for payment, acceptance, breach, liability, intellectual property, confidentiality, change, termination, dispute resolution, and other bid-response risks.
10. Map procurement requirements and scoring criteria into a response-file framework.
11. Identify missing materials, unclear requirements, conflicts, risks, and questions requiring user confirmation.
12. Output a structured analysis report and next-step recommendation.
13. Pause before any formal bid document generation, external-facing version, file modification, GitHub preparation, or publication.

## Key Rules

- Default to read-only analysis.
- Do not modify, move, delete, rename, overwrite, archive, or submit original files.
- Confirm scope before reading large batches of files.
- Confirm usage boundaries when materials involve quotation, customer, contract, qualification, supplier, project strategy, or other sensitive information.
- Keep tender document analysis separate from formal bid document generation.
- Analyze procurement requirements, scoring criteria, contract terms, delivery requirements, and response framework separately before synthesizing.
- Tie risk judgments to source terms where possible; mark unsupported or uncertain conclusions.
- Do not promise winning probability or bid success.
- Do not provide legal opinions. Treat contract review output as business risk identification that requires human or legal review.
- Do not perform automatic quotation calculation unless a separate authorized workflow is provided.
- Do not publish, sync, push, open pull requests, merge, or release to GitHub.

## Blocker Rules

Stop and report a blocker when any of the following occurs:

- file path does not exist;
- required files cannot be read;
- target materials are missing while the user requests complete analysis;
- procurement requirements, scoring criteria, or contract terms are incomplete and cannot be safely inferred;
- multiple document versions conflict and the authoritative version is unclear;
- the user asks to skip risk analysis;
- the user asks to directly generate a formal final bid document without confirming template, company materials, output format, and review boundary;
- the user asks for win-probability commitment or bid-winning promise;
- the user asks for legal opinion or guaranteed legal conclusion;
- materials contain quotation, customer, contract, qualification, supplier, project strategy, or other sensitive information and the user requests public release or GitHub publication;
- the user asks to modify, move, delete, rename, overwrite, archive, or submit original files without explicit confirmation;
- the task drifts into full software system development, frontend/backend architecture, database, deployment, MCP, plugin, or operations work;
- the user requests GitHub sync, push, pull request, merge, or release from this workflow.

When blocked, state the blocker, why it matters, what is needed to continue, and which step can resume after resolution.

## User Confirmation Nodes

Pause for user confirmation before:

- reading a large batch of local files;
- analyzing sensitive quotation, customer, contract, qualification, supplier, project strategy, or confidential materials beyond the stated scope;
- using company qualification, case, product, or service-capability materials in a response framework;
- generating a formal bid document, external-facing version, or submission-ready content;
- applying a specific company template or response format;
- modifying, moving, deleting, renaming, overwriting, archiving, or submitting any source file;
- creating a new Skill, README, examples, checklist, or other workflow artifact;
- preparing any GitHub-facing content;
- running GitHub sync, push, pull request, merge, or release actions.

## Acceptance Checklist

Before presenting an analysis as ready, verify:

- [ ] The analysis goal and reading scope are clear.
- [ ] Large-batch file reading was confirmed when applicable.
- [ ] Sensitive-material boundaries were confirmed when applicable.
- [ ] Source files were kept unchanged.
- [ ] Project basic information was extracted.
- [ ] Procurement requirements were identified.
- [ ] Scoring items and evaluation criteria were extracted.
- [ ] Qualification requirements were identified.
- [ ] Substantial response requirements were identified.
- [ ] Rejection clauses or bid-invalidity risks were identified.
- [ ] Contract clause risks were reviewed where contract terms exist.
- [ ] Delivery and acceptance requirements were extracted.
- [ ] A response-file framework was suggested.
- [ ] Missing materials and questions requiring confirmation were listed.
- [ ] Uncertain or inferred items were marked.
- [ ] Blockers were reported instead of bypassed.
- [ ] The output did not promise bid success, legal conclusions, automatic quotation, or formal final submission.
- [ ] No original files, other Skills, KnowledgeBase content, or GitHub resources were modified.

## Release-Readiness Judgment

Use these levels:

| Level | Meaning | Recommended Next Step |
|---|---|---|
| Not ready | Goal, source scope, required materials, blockers, or acceptance criteria are unclear. | Clarify inputs and boundaries. |
| Analysis ready | Authorized materials can be analyzed, but output has not been verified against real tender documents. | Run read-only analysis on a real sample. |
| Local MVP ready | The workflow can extract requirements, scoring items, risks, and response framework from a real sample. | Add README or examples only after user confirmation. |
| Validation ready | Multiple samples and pressure scenarios are defined, including missing files, version conflicts, sensitive materials, and skip-risk requests. | Run validation after approval. |
| Release-prep ready | Local validation passed and sensitive content has been removed or parameterized. | Prepare GitHub-facing materials only after explicit confirmation. |

This skill does not perform GitHub push, pull request, merge, or release actions.

## Suggested Response Shape

Use concise, structured sections:

```markdown
## Conclusion
- Recommendation:
- Current stage:
- Blocker:

## Source Scope
- Files reviewed:
- Missing files:
- Version or sensitivity notes:

## Tender Analysis
- Project basics:
- Procurement requirements:
- Qualification requirements:
- Substantial response requirements:
- Rejection risks:

## Scoring and Response
- Scoring items:
- Evidence or material requirements:
- Response framework:

## Contract and Delivery Risks
- Contract risks:
- Delivery requirements:
- Acceptance requirements:
- Questions for confirmation:

## Next Step
- Recommended action:
- User confirmation needed:
```
