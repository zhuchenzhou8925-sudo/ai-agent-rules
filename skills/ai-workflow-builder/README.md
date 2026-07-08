# ai-workflow-builder

## 定位

`ai-workflow-builder` 是用于设计、优化、拆分、合并 AI workflow / Codex Skill / Agent 规则的本机 skill。

它不只是 Skill MVP 设计框架，也用于管理真实开发闭环：从需求澄清、能力边界、文件结构、辅助文件、权限矩阵，到 GitHub draft PR、合并前只读复核、分支清理和闭环报告。

它的核心作用是帮助用户把可复用流程沉淀成可执行、可验证、可安全迭代的规则，而不是自动发布工具。

## 适用场景

- 新建业务 skill。
- 优化已有 skill。
- 拆分过大的 skill。
- 合并重复或相近 skill。
- 设计知识管理类 skill。
- 设计文档输出类 skill。
- 设计流程型 skill。
- 判断是否需要 README、examples、acceptance-checklist 或 templates。
- 复盘真实开发案例并反哺规则。
- 评估是否进入本地修改、GitHub 同步、PR 复核或闭环清理阶段。

## 不适用场景 / 边界

`ai-workflow-builder` 不负责自动执行高风险动作。

禁止默认执行：

- 自动生成对外发布版本。
- 自动 push。
- 自动创建 PR。
- 自动 merge。
- force push。
- 自动删除远程或本地分支。
- 绕过用户确认。
- 处理未授权敏感资料。
- 替代法律、投标、商务、报价、合同等专业确认。
- 将真实客户、项目、报价、合同、招标文件或隐私内容写入公开材料。

如用户提出上述动作，应先输出风险、确认节点和建议动作，等待明确授权。

## 标准使用流程

1. 只读理解用户目标。
2. 判断 skill 类型：business、workflow、knowledge-management、document-output 或 mixed。
3. 判断动作：Create、Improve、Split 或 Merge。
4. 设计能力边界和不适用场景。
5. 设计文件结构：`SKILL.md`、README、examples、acceptance checklist、templates 等。
6. 判断是否需要辅助文件，避免为了完整而新增无用文件。
7. 明确权限边界：只读分析、本地修改、GitHub 同步或对外发布。
8. 本地修改前确认具体文件和修改范围。
9. GitHub 同步前输出确认报告。
10. PR 合并前只读复核 PR 状态、范围、风险和敏感信息。
11. 用户确认后才进入合并或分支清理。
12. 合并后输出闭环报告。
13. 复盘真实案例，只记录脱敏、可复用的流程经验。

## 权限等级

| 等级 | 允许内容 | 必须确认 |
|---|---|---|
| Read-only analysis | 读取指定材料、检查现状、输出建议。 | 大量或敏感资料读取范围。 |
| Local modification | 修改用户明确授权的本地文件。 | 文件路径、修改范围、是否允许改辅助文件。 |
| GitHub sync | 准备分支、commit、push、PR 或同步方案。 | 分支、提交内容、push 目标、PR 信息。 |
| External release | 准备对外材料或公开说明。 | 脱敏结果、受众、发布渠道和最终授权。 |

用户确认一个等级，不代表自动确认更高等级。

## 典型输出

`ai-workflow-builder` 的输出应面向非技术用户，简洁给出判断和下一步。

常见输出包括：

- 当前判断。
- skill 类型。
- Create / Improve / Split / Merge 建议。
- 风险等级。
- 建议动作。
- 需要用户确认的节点。
- 文件结构建议。
- 辅助文件建议。
- 权限边界。
- 可执行提示词。
- 验收清单。
- PR 合并前只读复核报告。
- 合并后闭环报告。
- 案例复盘和规则反哺建议。

## GitHub 闭环边界

如进入 GitHub 流程，应坚持以下原则：

- 不直接修改 `main`。
- 使用 `draft/*` 分支。
- push 前输出确认报告。
- 创建 PR 前等待用户确认。
- PR 合并前只读复核。
- merge 前等待用户确认。
- squash merge 后如本地 `git branch -d` 被拒绝，不得直接 `git branch -D`。
- 强制删除本地分支前必须说明原因并等待确认。
- 闭环报告必须说明 PR、commit、main HEAD、远程/本地分支、当前分支、工作区和 blocker 状态。

## Blocker

遇到以下情况应暂停：

- 目标 skill 不明确。
- 用户要求越权操作。
- 涉及真实敏感资料且未授权脱敏。
- 可能覆盖已有 skill。
- 修改范围超出授权。
- GitHub 分支状态不清。
- PR 状态不清。
- merge conflict 未解决或状态未知。
- 本地工作区不干净且将进入 Git 操作。
- 需要强制删除分支但用户未确认。

暂停时应说明：blocker 是什么、为什么有风险、需要用户确认什么、下一步从哪里继续。
