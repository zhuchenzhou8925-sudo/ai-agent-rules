# bidding-document-analysis examples

本文件沉淀 `bidding-document-analysis` 的典型输入、输出骨架和 blocker 示例。

示例均为脱敏占位内容，不包含真实招标文件、采购文件、合同文件、报价、客户、资质、项目策略或原始资料。使用时应替换为用户明确授权读取的本地文件路径，并保持只读分析边界。

## Example 1: 标准只读分析请求

### User request

```markdown
请使用 bidding-document-analysis 对以下招标文件进行只读分析。

文件路径：
/path/to/authorized/tender-document.pdf

读取范围：
- 仅允许读取：/path/to/authorized/tender-document.pdf
- 不得读取：同目录下其他文件
- 如需要附件、合同模板或评分细则，请先暂停并说明原因

分析目标：
- 文件清单与章节结构
- 项目基本信息摘要
- 采购需求拆解
- 资格条件清单
- 实质性响应要求清单
- 废标风险清单
- 评分项提取表
- 合同条款风险清单
- 交付要求清单
- 响应文件编制框架
- 缺失资料清单
- 待确认问题清单
- 投标风险与下一步建议

执行边界：
- 只读分析
- 不创建、不修改、不删除任何原始资料
- 不生成正式投标文件终稿
- 不自动报价
- 不判断中标概率
- 不出具法律意见
- 不同步 GitHub
```

### Expected response shape

```markdown
## Conclusion
- Recommendation: 当前可进入投标前只读分析；不生成正式投标文件终稿。
- Current stage: Analysis ready
- Blocker: 无 / 或列明具体 blocker

## Source Scope
- Files reviewed:
  - /path/to/authorized/tender-document.pdf
- Files not reviewed:
  - 未读取同目录其他文件
- Version or sensitivity notes:
  - 未发现多个版本冲突；如后续补充附件需重新确认范围。

## Tender Analysis
- Project basics:
  - Project name:
  - Purchaser:
  - Submission deadline:
  - Delivery period:
- Procurement requirements:
  - Requirement:
  - Source:
  - Response implication:
- Qualification requirements:
  - Requirement:
  - Evidence needed:
  - Risk:
- Substantial response requirements:
  - Requirement:
  - Trigger:
  - Risk if missed:
- Rejection risks:
  - Clause:
  - Trigger:
  - Suggested check:

## Scoring and Response
- Scoring items:
  - Dimension:
  - Points:
  - Evidence:
  - Response focus:
- Evidence or material requirements:
  - Material:
  - Source:
  - Owner suggestion:
- Response framework:
  - Business section:
  - Technical section:
  - Price section:
  - Attachments:

## Contract and Delivery Risks
- Contract risks:
  - Clause type:
  - Business risk:
  - Confirmation needed:
- Delivery requirements:
  - Deliverable:
  - Deadline:
  - Acceptance basis:
- Acceptance requirements:
  - Standard:
  - Evidence:
  - Risk:
- Questions for confirmation:
  - Question:
  - Owner:
  - Priority:

## Next Step
- Recommended action:
- User confirmation needed:
```

## Example 2: 评分响应矩阵

Use this when scoring criteria are available and the user needs to map scoring items into response preparation work.

| Scoring item | Points | Response chapter | Evidence/material | Loss risk | Owner suggestion |
|---|---:|---|---|---|---|
| Technical solution completeness | 20 | Technical solution | Overall solution, architecture, implementation plan | High if only generic description is provided | Technical lead |
| Similar project experience | 10 | Business qualification | Contract, acceptance proof, case summary | Medium if proof materials are incomplete | Business team |
| Project team capability | 8 | Project organization | CVs, certificates, role matrix | Medium if role allocation is unclear | Project manager |
| After-sales service | 6 | Service commitment | Service plan, response SLA, support process | Low to medium if SLA is not quantified | Delivery team |

Output notes:

- Mark whether each scoring item is objective or subjective when the source document supports it.
- Do not invent points or scoring rules when the scoring table is missing.
- If scoring criteria are missing but the user asks for a complete scoring strategy, stop and report a blocker.

## Example 3: 合同风险矩阵

Use this when contract terms or a contract template are included in the authorized materials.

| Clause type | Risk description | Business impact | Suggested handling | Confirmation needed |
|---|---|---|---|---|
| Payment | Payment is tied to final acceptance without clear milestone payment | Cash-flow pressure and delivery risk | Confirm whether milestone payment can be clarified in response or negotiation notes | Business / finance |
| Acceptance | Acceptance standard is broad and lacks measurable criteria | Disputes may arise during delivery acceptance | Map deliverables to measurable acceptance evidence | Delivery / project |
| Liability | Liquidated damages may apply to delay without clear exceptions | Delay exposure may exceed controllable scope | Confirm force majeure, purchaser-side delay, and dependency handling | Legal / business |
| Intellectual property | Ownership of customized deliverables is unclear | Reuse and product boundary risk | Clarify background IP, project deliverables, and reuse boundaries | Legal / product |

Output notes:

- State clearly that this is business risk identification, not a legal opinion.
- Tie each risk to source terms where possible.
- If contract terms are missing, mark the section as missing rather than inferring risks.

## Example 4: 投标材料缺口矩阵

Use this when the analysis identifies missing qualification, case, personnel, product, authorization, or evidence materials.

| Missing material | Source requirement | Purpose | Impact level | Suggested next step |
|---|---|---|---|---|
| Similar project acceptance proof | Qualification or scoring requirement | Prove comparable delivery experience | High | Confirm available cases and acceptance documents |
| Project manager certificate | Personnel requirement | Support team capability scoring | Medium | Confirm candidate and certificate validity |
| Product capability statement | Technical response requirement | Match procurement functions | Medium | Prepare capability mapping table |
| Authorization letter | Bidder instruction or attachment requirement | Meet formal submission requirement | High | Confirm required format, signatory, and seal |

Output notes:

- Separate materials required for qualification review from materials used for scoring.
- Mark items that may cause rejection or invalid bid as high risk.
- Do not create, alter, or fabricate any qualification or proof material.

## Example 5: Blocker responses

### Missing file path

```markdown
## Blocker
- Blocker: The provided file path does not exist or cannot be accessed.
- Why it matters: The analysis cannot be source-backed without reading the authorized material.
- Needed to continue: Please provide a valid file path or confirm the correct location.
- Resume step: Source scope confirmation and file inventory.
```

### User asks to skip risk analysis

```markdown
## Blocker
- Blocker: The request asks to skip risk analysis.
- Why it matters: Risk identification is a required part of bidding document analysis, especially for rejection clauses, substantial response requirements, contract terms, and delivery obligations.
- Needed to continue: Confirm that risk analysis should remain in scope.
- Resume step: Rejection-risk, contract-risk, and delivery-risk extraction.
```

### User asks for final bid document directly

```markdown
## Blocker
- Blocker: The request asks for a formal final bid document without confirming template, company materials, quotation boundary, review responsibility, and output format.
- Why it matters: This skill supports pre-bid analysis and response framework suggestions, not submission-ready final documents.
- Needed to continue: Confirm template, authorized company materials, output format, review boundary, and whether this should move to a separate document-generation workflow.
- Resume step: Response-file framework suggestion.
```

### User asks for automatic quotation, win probability, legal opinion, or GitHub sync

```markdown
## Blocker
- Blocker: The request includes an out-of-scope action: automatic quotation / win-probability commitment / legal opinion / GitHub sync.
- Why it matters: The skill does not provide pricing commitments, bid-winning promises, lawyer-substitute conclusions, or publication workflows.
- Needed to continue: Remove the out-of-scope action and confirm the allowed analysis goal.
- Resume step: Structured bid analysis within the confirmed scope.
```

## Example 6: 本机验收复核请求

Use this after a read-only sample analysis has been completed and the user wants to verify whether the skill output is acceptable.

```markdown
请按 ./acceptance-checklist.md
对本次 bidding-document-analysis 输出进行本机验收复核。

复核边界：
- 只检查输出是否满足工作流验收要求
- 不重新分析原始招标文件，除非我明确授权
- 不修改原始资料
- 不修改 Skill 文件
- 不同步 GitHub

输出要求：
- 验收结论
- 已通过项
- 未通过项
- 需要补充确认的问题
- 是否可以进入下一轮真实样本或压力样本测试
```

Expected review summary:

```markdown
## 验收结论
- Result: Pass / Partial pass / Not pass
- Current maturity level:
- Main reason:

## 已通过项
- 

## 未通过项
- 

## 待确认问题
- 

## 下一步
- 
```
