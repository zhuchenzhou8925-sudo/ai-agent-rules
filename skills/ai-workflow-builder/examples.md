# ai-workflow-builder examples

本文件展示 `ai-workflow-builder` 如何指导 AI workflow / Codex Skill / Agent 规则的设计、优化、拆分、合并和 GitHub 闭环复核。

所有示例均为脱敏流程示例，不代表真实客户、项目、报价、合同或招标文件内容。示例不授权自动 push、PR、merge、release、force push 或自动删除分支。

## Example 1: Create a new business skill

### 场景

用户反复处理某类业务材料，希望沉淀为一个业务分析 skill。材料可能涉及商业判断、客户沟通、投标、合同或报价，但本阶段只抽象流程，不写入真实敏感内容。

### ai-workflow-builder 应输出

- 当前判断：适合新建 business skill。
- 建议动作：Create。
- 建议目录：`skills/example-business-analysis/`。
- 建议文件：
  - `SKILL.md`：必须。
  - `README.md`：如需给人类说明使用边界，可选。
  - `examples.md`：如需保留多个脱敏样例，可选。
  - `acceptance-checklist.md`：如流程有较多验收点，可选。
  - `templates/`：仅当输出有固定模板时使用。
- 能力边界：只做结构化分析和风险提示，不替代专业确认。
- 权限边界：默认只读分析；写入本地 skill 前需确认。
- 下一步：请确认 skill 名称、目标目录和允许创建的文件。

### 关键规则

- 不把真实业务资料写入 GitHub-bound 内容。
- 不承诺法律、报价、投标或商务最终结论。
- 不创建文件，直到用户确认本地修改范围。

## Example 2: Improve an existing skill

### 场景

用户已经有一个本机 skill，但真实使用中发现它缺少确认节点、敏感信息边界或 GitHub 发布前检查。

### ai-workflow-builder 应输出

- 当前判断：适合优化已有 skill。
- 建议动作：Improve。
- 差距：
  - 缺少 permission boundary。
  - 缺少 blocker。
  - 缺少 examples 或验收场景。
  - 缺少非技术用户响应格式。
- 修改范围：
  - 先只读复核现有文件。
  - 再列出建议修改文件。
  - 等用户确认后，只修改授权文件。
- 确认节点：
  - 是否允许修改 `SKILL.md`。
  - 是否允许同步修改 README、examples、acceptance checklist。
  - 是否允许后续进入 GitHub 流程。

### 关键规则

- 不做顺手重构。
- 不覆盖未授权文件。
- 不把“优化 skill”扩大成软件系统开发。

## Example 3: Split an oversized skill

### 场景

一个 skill 同时覆盖知识管理、文档生成、业务分析和 GitHub 流程，导致触发条件混乱、规则互相冲突、使用者难以判断该用哪个流程。

### ai-workflow-builder 应输出

- 当前判断：该 skill 可能过大。
- 建议动作：Split。
- 拆分建议：
  - 主入口 skill：保留分类、路由和确认节点。
  - 业务分析 skill：处理业务判断流程。
  - 文档输出 skill：处理 Word/PDF/Excel/PPT/Markdown 输出。
  - GitHub workflow skill：处理 draft PR、复核和闭环报告。
- 保留策略：
  - 原 skill 保留为上游判断入口。
  - 子 skill 只处理明确边界内的任务。
- 防止触发混淆：
  - 每个 skill 的 description 必须写清触发条件。
  - 非适用场景必须明确。

### 关键规则

- 拆分前只输出方案，不移动或删除文件。
- 需要用户确认拆分后的文件名、目录和迁移范围。
- 不复制敏感样本到新 skill。

## Example 4: Merge overlapping skills

### 场景

两个 skill 都在处理类似的“投标资料分析”或“文档归档”流程，触发条件相近，输出结构重复，blocker 规则不一致。

### ai-workflow-builder 应输出

- 当前判断：存在重复或相近 skill。
- 建议动作：Merge。
- 合并策略：
  - 对比两个 skill 的触发条件。
  - 保留更清晰的能力边界。
  - 合并 blocker 和确认节点。
  - 保留更完整的验收清单。
  - 给出旧入口的兼容说明。
- 废弃旧入口：
  - 只提出建议。
  - 不直接删除旧文件。
  - 等用户确认后再执行迁移或归档。

### 关键规则

- 不因名称相似就自动合并。
- 先确认是否存在不同使用场景。
- 合并过程中不得丢失更严格的安全边界。

## Example 5: GitHub draft PR workflow

### 场景

本机 skill 已完成本地修改和验证，用户希望准备同步到 GitHub 仓库。

### ai-workflow-builder 应输出

- 当前判断：可能进入 GitHub sync ready。
- 建议流程：
  1. 确认仓库、目标文件和工作区状态。
  2. 不直接修改 `main`。
  3. 使用 `draft/*` 分支。
  4. 限定修改范围。
  5. push 前输出确认报告。
  6. 用户确认后才 push。
  7. 用户确认后才创建 PR。
  8. PR 合并前只读复核。
  9. 用户确认后才 merge。
  10. 合并后同步 `main`。
  11. 清理远程和本地 draft 分支。
  12. 输出闭环报告。

### push 前确认报告应包含

- 当前分支。
- 目标远程仓库。
- changed files。
- 修改摘要。
- 敏感信息检查。
- 风险等级。
- 建议 PR 标题和正文。
- 是否等待用户确认。

### 关键规则

- 不自动 push。
- 不自动创建 PR。
- 不自动 merge。
- 不 force push。

## Example 6: PR merge review

### 场景

用户提供一个 PR，希望判断是否可以合并。

### ai-workflow-builder 应输出

- 当前判断：进入 PR review ready。
- 只读复核项：
  - PR 编号。
  - 当前状态。
  - 是否 Draft。
  - base / head。
  - commit 数量。
  - changed files。
  - 是否仅修改授权范围。
  - 是否包含敏感信息。
  - 能力边界是否清楚。
  - 是否存在 merge conflict。
  - 风险等级。
  - 是否建议合并。
  - 是否仍需用户确认。

### 示例结论格式

```markdown
当前判断：可以进入合并前确认，但不能自动合并。
风险等级：低 / 中 / 高。
建议动作：等待用户明确确认 merge 方式。
需要确认：是否使用 squash merge，以及是否合并后清理 draft 分支。
```

### 关键规则

- PR 状态不清时不得建议合并。
- 有冲突时不得建议合并。
- 合并前必须等待用户确认。

## Example 7: Squash merge cleanup

### 场景

PR 已经 squash merge。随后清理本地 draft 分支时，`git branch -d` 被拒绝。

### ai-workflow-builder 应输出

- 当前判断：需要用户确认是否强制删除本地分支。
- 原因说明：
  - squash merge 会在 `main` 上生成新的 commit。
  - 本地 draft 分支原 commit 可能不是 `main` 的直接祖先。
  - 因此 Git 可能拒绝安全删除。
- 复核项：
  - PR 是否已合并。
  - `main` 是否已同步。
  - draft 分支是否还有未保留工作。
  - 工作区是否干净。
- 建议动作：
  - 不直接执行 `git branch -D`。
  - 等用户明确确认后再强制删除本地分支。

### 关键规则

- `git branch -d` 被拒绝后，不得自动 `git branch -D`。
- 强制删除是用户确认动作。

## Example 8: Case review and feedback loop

### 场景

一个 sanitized `bidding-document-analysis` skill PR 被用作流程验证案例。该案例只验证流程，不写入真实客户、项目、报价、合同或招标文件内容。

### 该案例验证了

- draft 分支开发。
- push 前确认报告。
- PR 创建。
- 合并前只读复核。
- 用户确认后 squash merge。
- squash merge 后本地分支清理。
- 闭环报告。

### ai-workflow-builder 应输出

- 当前判断：该案例可用于反哺流程规则。
- 可沉淀经验：
  - GitHub 闭环需要明确分阶段确认。
  - PR 合并前必须只读复核。
  - squash merge 后本地分支清理需要单独确认。
  - 闭环报告要包含 PR、commit、main HEAD、分支和工作区状态。
- 不应沉淀：
  - 真实客户信息。
  - 真实项目名称。
  - 报价、合同、招标文件原文。
  - 私有路径或凭据。

### 关键规则

- 只记录脱敏流程经验。
- 只在用户确认后修改 skill。
- 不把案例写成业务宣传材料。
