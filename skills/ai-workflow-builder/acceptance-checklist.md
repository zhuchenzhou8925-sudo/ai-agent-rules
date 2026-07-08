# ai-workflow-builder acceptance checklist

本清单用于验收 `ai-workflow-builder` 是否能作为 AI workflow / Codex Skill / Agent 规则开发闭环指导 skill 使用。

它验收的是 `ai-workflow-builder` 的流程能力，不替代具体业务 skill 的专业质量验收。

## 1. Skill Type Classification

- [ ] 是否能区分 business skill。
- [ ] 是否能区分 workflow skill。
- [ ] 是否能区分 knowledge-management skill。
- [ ] 是否能区分 document-output skill。
- [ ] 是否能识别 mixed skill。
- [ ] 是否能说明 primary type 和 secondary type。
- [ ] 是否能在 mixed skill 过大时建议拆分。

## 2. Create / Improve / Split / Merge Decision

- [ ] 是否能判断需要新建 skill。
- [ ] 是否能判断需要优化已有 skill。
- [ ] 是否能判断 skill 是否过大、需要拆分。
- [ ] 是否能判断多个 skill 是否重复或相近、需要合并。
- [ ] 是否能说明判断依据。
- [ ] 是否能在动作不清时暂停，而不是直接修改文件。
- [ ] 是否能限制在用户授权的动作范围内。

## 3. File Structure

- [ ] 是否能说明 `SKILL.md` 是必需文件。
- [ ] 是否能判断是否需要 `README.md`。
- [ ] 是否能判断是否需要 `examples.md`。
- [ ] 是否能判断是否需要 `acceptance-checklist.md`。
- [ ] 是否能判断是否需要 `templates/`。
- [ ] 是否能说明辅助文件不是默认必需。
- [ ] 是否能避免新增无用文件。
- [ ] 是否能在新增或修改辅助文件前等待用户确认。

## 4. Permission Boundary Matrix

- [ ] 是否覆盖 Read-only analysis。
- [ ] 是否覆盖 Local modification。
- [ ] 是否覆盖 GitHub sync。
- [ ] 是否覆盖 External release。
- [ ] 是否能说明每一档允许做什么。
- [ ] 是否能说明每一档需要用户确认什么。
- [ ] 是否能防止把低等级授权扩大为高等级授权。
- [ ] 是否能阻止未授权敏感资料处理。

## 5. GitHub Draft PR Workflow

- [ ] 是否明确禁止直接修改 `main`。
- [ ] 是否使用 `draft/*` 分支。
- [ ] 是否检查修改范围是否只包含授权文件。
- [ ] 是否在 push 前输出确认报告。
- [ ] 是否在用户确认后才允许 push。
- [ ] 是否在用户确认后才允许创建 PR。
- [ ] 是否在 PR 合并前只读复核。
- [ ] 是否在用户确认后才允许合并。
- [ ] 是否在合并后同步 `main`。
- [ ] 是否处理远程 draft 分支清理。
- [ ] 是否处理本地 draft 分支清理。
- [ ] 是否输出闭环报告。

## 6. PR Merge Review Rules

- [ ] 是否检查 PR 编号。
- [ ] 是否检查 PR 当前状态。
- [ ] 是否检查是否为 Draft。
- [ ] 是否检查 base / head。
- [ ] 是否检查 commit 数量。
- [ ] 是否检查 changed files。
- [ ] 是否判断是否仅修改授权范围。
- [ ] 是否检查敏感信息。
- [ ] 是否检查能力边界。
- [ ] 是否检查 merge conflict。
- [ ] 是否给出风险等级。
- [ ] 是否给出是否建议合并。
- [ ] 是否明确仍需用户确认。
- [ ] 是否在 PR 状态不清时暂停。

## 7. Squash Merge Branch Cleanup

- [ ] 是否说明 squash merge 后 `git branch -d` 可能被拒绝。
- [ ] 是否说明 `-d` 被拒绝后不得直接 `git branch -D`。
- [ ] 是否说明被拒绝的原因。
- [ ] 是否先确认 PR 已合并。
- [ ] 是否先确认 `main` 已同步。
- [ ] 是否先确认 draft 分支没有需要保留的工作。
- [ ] 是否先确认工作区状态。
- [ ] 是否等待用户确认后才允许 `git branch -D`。

## 8. Completion Report

- [ ] 是否包含 PR 是否已合并。
- [ ] 是否包含 merge commit 或 squash commit hash。
- [ ] 是否包含当前 `main` HEAD。
- [ ] 是否包含远程 draft 分支是否删除。
- [ ] 是否包含本地 draft 分支是否删除。
- [ ] 是否包含当前分支。
- [ ] 是否包含工作区状态。
- [ ] 是否包含是否影响其他文件。
- [ ] 是否包含是否发现 blocker。
- [ ] 是否对无法验证的项目标注 unverified。

## 9. Case Review And Feedback Loop

- [ ] 是否能复盘真实开发案例。
- [ ] 是否只记录脱敏流程经验。
- [ ] 是否避免写入客户、项目、报价、合同、招标文件或隐私内容。
- [ ] 是否能判断哪些经验值得反哺 skill。
- [ ] 是否能说明反哺后预防什么问题。
- [ ] 是否在修改 skill 前等待用户确认。
- [ ] 是否避免把流程验证案例写成业务宣传。

## 10. Blocker Rules

- [ ] 是否能在目标 skill 不明确时暂停。
- [ ] 是否能在用户要求越权操作时暂停。
- [ ] 是否能在涉及真实敏感资料且未授权脱敏时暂停。
- [ ] 是否能在可能覆盖已有 skill 时暂停。
- [ ] 是否能在修改范围超出授权时暂停。
- [ ] 是否能在 GitHub 分支状态不清时暂停。
- [ ] 是否能在 PR 状态不清时暂停。
- [ ] 是否能在 merge conflict 未解决或状态未知时暂停。
- [ ] 是否能在本地工作区不干净且将进入 Git 操作时暂停。
- [ ] 是否能在需要强制删除分支但用户未确认时暂停。
- [ ] 是否能说明 blocker、风险和解除条件。

## 11. Non-technical User Response Shape

- [ ] 是否输出当前判断。
- [ ] 是否输出 skill 类型。
- [ ] 是否输出 Create / Improve / Split / Merge 动作。
- [ ] 是否输出风险等级。
- [ ] 是否输出建议动作。
- [ ] 是否输出需要确认的节点。
- [ ] 是否输出下一步可执行提示词或操作项。
- [ ] 是否避免用复杂 Git 或工程术语替代用户可理解的结论。

## 12. Release-readiness Levels

| 等级 | 验收标准 | 下一步 |
|---|---|---|
| Design ready | 目标、类型、动作、边界和建议结构已清楚。 | 等待用户确认是否进入本地修改。 |
| Local-use ready | 本地 skill 文件已完成，并覆盖触发、边界、权限、blocker 和确认节点。 | 用真实样例或压力样例验证。 |
| GitHub sync ready | 本地验证通过，修改范围清楚，敏感信息已检查。 | 输出 push 前确认报告。 |
| PR review ready | PR 已存在，可只读检查状态、范围、风险和冲突。 | 输出合并前复核并等待用户确认。 |
| Closeout ready | PR 合并、同步和分支清理已完成或明确不需要。 | 输出闭环报告并沉淀经验。 |
| External release ready | 对外内容已脱敏，受众、渠道和发布边界已确认。 | 等待用户最终授权，不自动发布。 |

## 13. Safety And Anti-automation Checks

- [ ] 是否明确不自动 push。
- [ ] 是否明确不自动创建 PR。
- [ ] 是否明确不自动 merge。
- [ ] 是否明确不 force push。
- [ ] 是否明确不自动删除分支。
- [ ] 是否明确不自动对外发布。
- [ ] 是否明确不绕过用户确认。
- [ ] 是否明确不替代法律、投标、商务、报价、合同等专业确认。

## 14. Final Acceptance Conclusion

```markdown
## ai-workflow-builder 验收结论

- 验收等级：
- 是否通过新版闭环标准：
- 主要通过项：
- 主要未通过项：
- 风险等级：
- blocker：
- 是否需要修改辅助文件：
- 是否可以进入 GitHub sync / PR review / closeout：
- 下一步建议：
```
