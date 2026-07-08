---
name: ai-workflow-builder
description: Use when the user wants to turn a repeated business process, knowledge-work process, document process, rule-based task, Codex Skill, or agent rule workflow into a reusable AI workflow design, validation plan, local Skill update plan, or GitHub release-readiness review.
---

# AI Workflow Builder

## Purpose

Use this skill to help the user turn a repeated AI-assisted workflow into a practical Codex Skill or agent workflow.

Focus on workflow design, Skill scope, rule formalization, permission boundaries, validation, GitHub release-readiness review, and post-merge learning. Do not turn this skill into a full software development, automatic publishing, automatic merge, or force-push tool.

## Trigger Conditions

Use this skill when the user asks to:

- create or design a new Codex Skill;
- improve, split, merge, or validate an existing Skill;
- turn a repeated business, knowledge, document, or rules-based process into a reusable AI workflow;
- extract reusable rules from a proven work session;
- define a Skill's inputs, outputs, workflow steps, blockers, confirmation points, and acceptance checklist;
- judge whether a Skill is ready for local use, GitHub sync, PR creation, PR merge review, or release preparation;
- prepare README, examples, acceptance checklist, or template recommendations for a Skill.

## Applicable Scenarios

- Codex Skill design and revision planning.
- Agent rule workflow extraction.
- Skill type classification.
- Skill file structure planning.
- Execution rule design.
- Permission boundary and confirmation design.
- Blocker and pause-rule design.
- Manual validation and acceptance design.
- GitHub draft PR workflow guidance.
- PR merge-readiness review.
- Post-merge completion report design.
- Real-case review and feedback into the Skill.

## Non-Applicable Scenarios

Do not use this skill for:

- complete software system development;
- frontend or backend architecture design;
- database design;
- deployment, operations, or infrastructure work;
- MCP tool development;
- plugin development;
- automatic GitHub push, pull request, merge, force push, branch force-delete, or release execution;
- automatic publication to external users or public repositories;
- bypassing missing-path, permission, sensitive-data, rule-conflict, PR-state, branch-state, or Git-state blockers.

If the user's request is actually software development or GitHub publishing execution, route to the relevant engineering or GitHub workflow after explicit user confirmation.

## Skill Type Classification

Classify the requested Skill before designing or modifying it.

| Type | Use When | Typical Outputs | Boundary Risk |
|---|---|---|---|
| Business skill | The workflow analyzes business, bidding, quotation, contract, customer, or project materials. | Business judgment framework, risk list, decision checklist. | Sensitive commercial data, legal/financial overclaiming. |
| Workflow skill | The workflow coordinates repeatable steps, confirmations, tools, or Git operations. | Standard process, decision nodes, blockers, completion report. | Over-automation or skipped confirmation. |
| Knowledge-management skill | The workflow organizes, extracts, or converts materials into reusable knowledge. | Taxonomy, metadata model, source links, knowledge notes. | Mixing source archives with knowledge artifacts. |
| Document-output skill | The workflow creates or edits Word, PDF, Excel, PPT, Markdown, or template-driven outputs. | Output structure, style rules, templates, acceptance checks. | Unapproved writes, format loss, private content in outputs. |
| Mixed skill | The workflow combines two or more categories. | Primary type plus secondary modules and explicit boundaries. | Scope creep and overloaded SKILL.md. |

For mixed skills, name the primary type and list secondary types. If one SKILL.md would become hard to follow, recommend splitting.

## Action Decision: Create / Improve / Split / Merge

Decide the action before writing or editing.

| Action | Choose When | Required Check |
|---|---|---|
| Create a new Skill | No existing Skill covers the repeated workflow and the reuse value is stable. | Confirm name, target directory, scope, and write permission. |
| Improve an existing Skill | A Skill exists but misses rules, examples, blockers, or acceptance checks. | Confirm exact file scope and avoid unrelated rewrites. |
| Split an oversized Skill | One Skill covers unrelated types, has too many conditional branches, or creates conflicting permissions. | Propose split names and migration plan before editing. |
| Merge similar Skills | Two or more Skills overlap heavily and create duplicate triggers or conflicting rules. | Compare triggers, preserve strongest blockers, and confirm merge scope. |

If the user asks for a broad "make it better" change, first produce a scoped improvement plan and wait for confirmation before editing.

## Input Types

Collect only the inputs needed for the current phase:

- workflow goal: what repeated task should become reusable;
- user group: who will use the Skill or workflow;
- skill type: business, workflow, knowledge-management, document-output, or mixed;
- action type: create, improve, split, merge, validate, sync, review, or close out;
- trigger examples: what users might say to invoke it;
- source process: prior work session, manual workflow, rules, templates, or examples;
- input materials: folders, documents, prompts, checklists, or constraints;
- output expectations: design brief, SKILL.md draft, auxiliary file advice, validation checklist, PR review, or closeout report;
- permission boundaries: read-only, local modification, GitHub sync, or external release;
- safety boundaries: forbidden actions, sensitive content, Git rules, and confirmation requirements;
- acceptance criteria: what must be true before the workflow is considered usable.

If critical inputs are missing and a safe assumption would change the workflow boundary, stop and ask for clarification.

## Output Types

Produce one or more of these outputs:

- Skill design brief;
- Skill type and action decision;
- proposed Skill name and trigger description;
- applicable and non-applicable scenario list;
- input and output model;
- standard execution workflow;
- permission boundary matrix;
- blocker rules;
- user confirmation nodes;
- acceptance checklist;
- suggested file structure;
- README, examples, acceptance checklist, or template recommendations;
- release-readiness judgment;
- PR merge-readiness review;
- completion report;
- case review and feedback recommendation;
- next-step prompt or operation for the user to approve.

Clearly label whether the output is a design proposal, creation-ready draft, validation result, PR review, release-preparation judgment, or completion report.

## Skill File Structure

Use the smallest structure that supports the Skill.

```text
skill-name/
  SKILL.md
  README.md
  examples.md
  acceptance-checklist.md
  templates/
```

Rules:

- `SKILL.md` is required and must contain the core instructions that future Codex instances need at runtime.
- `README.md` is optional and should be used only when the Skill needs human-facing usage guidance, installation notes, or release-facing explanation.
- `examples.md` is optional and should be used when realistic trigger examples, sample outputs, or pressure cases would be too long for SKILL.md.
- `acceptance-checklist.md` is optional and should be used when validation is substantial enough to deserve a separate checklist.
- `templates/` is optional and should be used only when the Skill repeatedly produces fixed-format deliverables or prompt/document templates.
- Do not add auxiliary files by default. Recommend them only when they reduce SKILL.md bloat or improve validation, reuse, or safe release review.

## SKILL.md Structure

Recommend this structure for most Skills:

1. Purpose
2. Trigger Conditions
3. Applicable Scenarios
4. Non-Applicable Scenarios
5. Inputs
6. Outputs
7. Execution Flow
8. Permission Boundaries
9. Blocker Rules
10. Confirmation Nodes
11. Acceptance Checklist
12. Suggested Response Shape

For release-sensitive Skills, add GitHub workflow, PR review, branch cleanup, completion report, and case feedback sections. Keep detailed examples or long checklists in auxiliary files when needed.

## Supporting Files Decision Rules

Use these rules before recommending or creating auxiliary files.

| File | Add When | Do Not Add When |
|---|---|---|
| README.md | A human needs concise usage, release, or repository-facing context. | SKILL.md alone is enough for runtime use. |
| examples.md | There are multiple realistic trigger examples, pressure tests, or sample outputs. | One short example can fit cleanly in SKILL.md. |
| acceptance-checklist.md | Validation is multi-step, risk-sensitive, or reused before PR/release. | Acceptance checks are short and local to SKILL.md. |
| templates/ | Outputs follow fixed reusable formats such as reports, checklists, prompts, or document structures. | The workflow is judgment-based and does not need fixed files. |
| scripts/ | Deterministic repeated operations are safer as code. | The work is mostly judgment, review, or writing. |
| references/ | Domain knowledge or API detail is large and loaded only when needed. | The reference would duplicate SKILL.md. |

When official or local skill guidance discourages extra files, prefer SKILL.md only unless the user's release, validation, or reuse goal clearly justifies auxiliary files.

## Standard Execution Flow

1. Identify the user's goal and classify the task as Skill design, workflow extraction, rules formalization, validation planning, PR review, or closeout.
2. Classify the Skill type: business, workflow, knowledge-management, document-output, or mixed.
3. Decide the action: create, improve, split, merge, validate, sync, review, or close out.
4. Restate the boundary in one short conclusion, especially what is excluded.
5. Collect or infer representative trigger examples, expected inputs, expected outputs, and safety limits.
6. Extract the repeated workflow into stable steps.
7. Define applicable scenarios, non-applicable scenarios, and explicit exclusions.
8. Define input and output structures.
9. Define permission boundaries, including read-only defaults, local write scope, GitHub restrictions, and publication restrictions.
10. Define blockers that require stopping instead of continuing with assumptions.
11. Define confirmation nodes before writes, formal filing, GitHub operations, destructive actions, branch deletion, publishing, or scope expansion.
12. Define acceptance checks and pressure scenarios.
13. Judge whether the workflow is ready for Skill creation, local modification, validation, GitHub sync, PR review, or release preparation.
14. Pause when user confirmation is required. Do not continue into file modification, GitHub sync, PR creation, merge, branch cleanup, or publication without explicit approval.

## Permission Boundary Matrix

Treat permissions as four separate levels.

| Level | Allowed By Default | Requires User Confirmation | Forbidden Without Separate Approval |
|---|---|---|---|
| Read-only analysis | Read specified files, inspect repo status, summarize current state, propose changes. | Reading large or sensitive material sets. | Moving, deleting, rewriting, committing, pushing, merging, publishing. |
| Local modification | Edit only explicitly authorized local files. | Exact file path, write scope, and whether auxiliary files may change. | Modifying unapproved files, formal KnowledgeBase writes, destructive file operations. |
| GitHub sync | Prepare branch, commit, push, PR, or sync plan. | Branch name, commit scope, push target, PR title/body, changed files report. | Direct main edits, force push, auto PR creation, auto merge. |
| External release | Prepare public-facing or organization-facing materials. | Final sanitized content, audience, release channel, and user approval. | Publishing real customer, contract, bidding, quotation, credential, or private content. |

If the user approves one level, stay inside that level. Do not infer approval for higher levels.

## GitHub Draft PR Workflow

Use this workflow only as guidance. Do not execute GitHub actions unless the user separately confirms the exact operation.

1. Confirm the repository, target files, and clean working state.
2. Do not modify `main` directly for Skill development or release preparation.
3. Create or use a `draft/*` branch for the proposed Skill work.
4. Keep the modification scope limited to the authorized Skill files.
5. Before push, output a confirmation report covering branch, changed files, summary, risk level, sensitive-content check, and proposed PR title/body.
6. Push only after explicit user confirmation.
7. Create a PR only after explicit user confirmation; default to a draft PR when review is still needed.
8. Before merge, perform a read-only PR merge review.
9. Merge only after explicit user confirmation. Do not auto-merge.
10. After merge, sync local `main` with the remote main branch.
11. Delete the remote `draft/*` branch only after confirming merge state and user approval or repository workflow expectations.
12. Delete the local `draft/*` branch only after confirming it is no longer needed.
13. Output a completion report.

Never force push, merge, publish, or delete branches automatically.

## PR Merge Review Rules

Before recommending a PR merge, perform a read-only review and report:

- PR number;
- current PR state;
- whether the PR is Draft;
- base branch and head branch;
- commit count;
- changed files;
- whether changes stay within the authorized scope;
- sensitive information check;
- capability boundary check;
- merge conflict status;
- risk level;
- whether merge is recommended;
- whether user confirmation is still required.

If any required PR state cannot be confirmed, mark it as unknown and pause instead of recommending merge.

## Squash Merge Branch Cleanup Rules

After a squash merge, local branch cleanup may be different from a normal merge.

- `git branch -d` can be refused because the local branch tip is not an ancestor of `main` after squash merge.
- If `git branch -d` is refused, do not run `git branch -D` automatically.
- Explain that squash merge creates a new commit on `main`, so Git may not consider the local draft branch safely merged.
- Confirm that the PR is merged, `main` is synced, and no needed work remains on the draft branch.
- Wait for explicit user confirmation before using `git branch -D`.

Forced local branch deletion is a user-confirmed cleanup action, not an automatic step.

## Completion Report Rules

When a GitHub PR workflow is closed out, report:

- whether the PR has been merged;
- merge commit or squash commit hash;
- current `main` HEAD;
- whether the remote `draft/*` branch was deleted;
- whether the local `draft/*` branch was deleted;
- current local branch;
- working tree status;
- whether any files outside the approved scope were affected;
- whether any blocker remains.

If any item cannot be verified, mark it as unverified and explain why.

## Blocker Rules

Stop and report a blocker when any of the following occurs:

- the target Skill is unclear;
- the workflow goal is unclear;
- the user asks for an action beyond the confirmed permission level;
- the target Skill name or scope conflicts with an existing Skill;
- the requested change may overwrite an existing Skill;
- a required local path does not exist;
- filesystem permission is missing;
- the request requires writing files but the user has not confirmed the write scope;
- the request would modify an existing Skill without explicit approval;
- the request would modify a formal KnowledgeBase without explicit approval;
- real sensitive material is involved and the user has not authorized safe handling or sanitization;
- sensitive, private, customer, contract, quotation, bidding, credential, token, or secret content may be included in GitHub-bound or release-bound output;
- the modification scope exceeds the authorized file list;
- GitHub branch state is unclear;
- PR state is unclear;
- merge conflict status is unknown or conflicts are unresolved;
- local working tree is not clean and the task involves sync, commit, push, PR, merge, or branch cleanup;
- forced local branch deletion is needed but the user has not confirmed it;
- the user asks to skip required validation, confirmation, or safety checks;
- the request drifts into full software architecture, deployment, MCP, plugin, or database design;
- acceptance criteria are missing and cannot be safely inferred.

When blocked, state the blocker, why it matters, the risk level, and the exact user decision or environmental change needed.

## User Confirmation Nodes

Pause for confirmation before:

- creating a new Skill file or folder;
- modifying an existing Skill;
- writing README, examples, acceptance checklist, templates, scripts, references, or release notes;
- reading a large or sensitive local material set;
- writing to a formal KnowledgeBase;
- moving, deleting, renaming, overwriting, or archiving files;
- preparing GitHub-facing content from private material;
- creating or switching release branches when the branch target is unclear;
- committing, pushing, opening a pull request, marking a PR ready, merging, or releasing;
- deleting a remote branch;
- force-deleting a local branch with `git branch -D`;
- publishing external-facing content;
- expanding from Skill/workflow guidance into software development.

If the user has already confirmed a narrow action, stay within that exact scope.

## Acceptance Checklist

Before calling a Skill workflow ready, verify:

- the Skill name uses lowercase letters, digits, and hyphens only;
- the Skill type and action decision are explicit;
- trigger conditions are specific enough for discovery;
- applicable and non-applicable scenarios are clear;
- inputs and outputs are explicit;
- execution flow can be followed step by step;
- permission boundaries are explicit;
- blocker rules stop unsafe or ambiguous work;
- user confirmation nodes are listed;
- supporting files are justified or explicitly not needed;
- at least three realistic trigger examples can be tested;
- at least one pressure scenario tests whether the agent refuses to bypass confirmation, validation, GitHub safety rules, or branch cleanup safety;
- the design does not become full software development or automatic publishing;
- sensitive-content and GitHub boundaries are explicit;
- the next step is clear: revise design, edit local Skill, validate, prepare GitHub sync, review PR, merge after confirmation, or close out.

## Release-Readiness Judgment

Use these levels:

| Level | Meaning | Recommended Next Step |
|---|---|---|
| Not ready | Goal, scope, blockers, or acceptance criteria are unclear. | Clarify and redesign. |
| Design ready | Workflow design is complete, but no Skill file has been created or validated. | Confirm creation or edit scope. |
| Local MVP ready | SKILL.md exists and covers triggers, scope, flow, blockers, confirmations, and acceptance checks. | Decide whether auxiliary files or examples are needed. |
| Validation ready | Test scenarios and pressure cases are defined. | Run manual or agent-based validation after approval. |
| GitHub sync ready | Local validation passed, scope is clean, and sensitive information has been checked. | Prepare branch and push confirmation report. |
| PR review ready | PR exists and can be reviewed read-only. | Perform PR merge review and wait for user confirmation. |
| Closeout ready | Merge and cleanup are complete or explicitly not needed. | Produce completion report and capture learning. |

Do not perform GitHub push, pull request, merge, branch deletion, force deletion, or release actions from this skill unless the user separately requests and confirms those actions through an appropriate GitHub workflow.

## Case Review And Feedback Loop

After a real Skill development workflow, review the case and feed durable lessons back into the Skill only after user approval.

Use this loop:

1. Identify what the case tested: design, local edits, auxiliary files, validation, GitHub sync, PR review, merge, cleanup, or closeout.
2. Record only sanitized process lessons. Do not record customer names, project names, original bidding text, contract text, quotation data, credentials, private paths beyond approved working targets, or other sensitive material.
3. Compare the case against current Skill rules.
4. Add or revise rules only when the lesson is reusable across future workflows.
5. Keep the rule concise and operational.
6. Report what changed and what future failure it prevents.

A sanitized `bidding-document-analysis` Skill PR was used as the first validation case. It validated the draft branch, PR, pre-merge read-only review, squash merge, local branch cleanup, and completion report workflow. Treat it as a process validation case, not as business promotion or reusable customer content.

## Suggested Response Shape

Respond for non-technical users with concise, copy-ready sections:

```markdown
## Current Judgment
- Task type:
- Skill type:
- Action:
- Current stage:

## Risk
- Risk level:
- Main risks:
- Blocker:

## Recommended Action
- What I recommend:
- Why:
- Scope:

## Confirmation Needed
- Needs confirmation:
- Exact action to confirm:

## Next Step
- Suggested prompt or operation:
```

For completion reports, use:

```markdown
## Completion Report
- Modified successfully:
- Actual files changed:
- Added files:
- GitHub repository changed:
- Commit / push / PR:
- PR merged:
- Merge or squash commit:
- Current main HEAD:
- Remote draft branch deleted:
- Local draft branch deleted:
- Current branch:
- Working tree status:
- Other files affected:
- Blocker:
- Next recommended step:
```

## Relationship to Domain Skills

This skill is an upstream workflow-builder. Domain Skills solve specific operational problems. This skill helps extract the method behind such work and turn it into reusable Skill or agent workflow guidance.

Do not modify any domain Skill while using this skill unless the user explicitly asks for that separate change.
