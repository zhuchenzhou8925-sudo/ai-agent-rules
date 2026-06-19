> 来源说明：本文件由本机现有智能体配置整理而来，用于 GitHub 跨设备同步和 Codex 调用。
> 脱敏说明：已将本机绝对路径、真实日志路径和输出目录参数化；不得包含客户资料、合同、报价、招采文件、密钥或未脱敏业务资料。

# 测试用例与验收规则

## 来源与用途说明
- 来源文件：`<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-测试用例与验收规则.md`
- 处理方式：脱敏后复制
- 用途：作为 GitHub 跨设备同步和 Codex 调用的脱敏规则副本。

# Obsidian 测试用例与验收规则

# 文件用途

本文件用于定义 Obsidian 规则闭环的测试输入、测试输出、静态检查、自动修正和验收报告标准。

# 适用范围

适用于规则生成、规则补齐、测试样例生成、测试输出生成和闭环报告，不适用于正式资料迁移。

# 输入要求

- 测试输入必须为虚构内容。
- 测试输入不得复制、改写或映射正式资料。
- 测试输入应覆盖项目背景、目标、任务、技术路线、交付成果、风险、待确认事项和来源说明。

# 输出要求

- 必须生成测试输入、测试输出和测试报告。
- 测试输出必须包含 YAML frontmatter、来源说明、状态说明、双链、标签、未确认事项、下一步建议、自检结果和测试状态。
- 测试报告必须说明是否达到沙盒闭环可用状态。

# frontmatter 要求

测试输出必须包含：

```yaml
review:
  human_checked: false
  migration_suggested: false
  migration_confirmed: false
test:
  is_test_output: true
  test_round: 1
```

# 正文结构要求

测试输出正文必须包含：

- 来源说明；
- 状态说明；
- 主体内容；
- Obsidian 双链；
- 标签；
- 未确认事项；
- 下一步建议；
- 自检结果；
- 测试状态说明。

# 双链与标签要求

- 双链检查标准：是否存在 `[[页面名]]`。
- 标签检查标准：是否存在 `#测试` 和至少一个主题标签。

# 目录归属规则

测试目录结构固定为：

```text
<TEST_WORKSPACE>/input/
<TEST_WORKSPACE>/output/
<TEST_WORKSPACE>/report/
```

不得将测试文件写入正式知识库目录。

# 禁止事项

- 禁止写临时脚本。
- 禁止绕过 blocker。
- 禁止修改 `Codex_Control`。
- 禁止修改原始资料。
- 禁止迁移正式知识库内容。
- 禁止将测试输出标记为已人工检查、建议迁移或确认迁移。

# 自检清单

| 检查项 | 要求 |
|---|---|
| 结构检查 | frontmatter、标题、来源、状态、标签、双链齐全 |
| 合规检查 | 未写正式目录、未改原始资料、未改控制文件 |
| Obsidian 检查 | Markdown 可读、双链和标签格式正确 |
| 修正检查 | 允许范围内问题已修正 |

# 测试样例要求

必须生成：

- `test-project-material-001.md`
- `test-project-material-002.md`
- `test-source-doc-index.md`

必须生成：

- `test-project-note.md`
- `test-moc.md`
- `test-knowledge-card.md`
- `test-source-index.md`

# 验收标准

- 完成至少一轮静态检查。
- 发现的问题已在允许范围内修正。
- 生成闭环测试报告。
- 报告结论只能为：已达到沙盒闭环可用状态；部分达到，需要用户确认后继续完善；未达到，存在 blocker。
