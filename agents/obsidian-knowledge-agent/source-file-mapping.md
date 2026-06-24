> 来源说明：本文件由本机现有智能体配置整理而来，用于 GitHub 跨设备同步和 Codex 调用。
> 脱敏说明：已将本机绝对路径、真实日志路径和输出目录参数化；不得包含客户资料、合同、报价、招采文件、密钥或未脱敏业务资料。

# 智能体配置文件映射表

| 原始文件路径 | 原始文件名 | GitHub 目标路径 | 目标文件名 | 中文说明 | 处理方式 | 备注 |
|---|---|---|---|---|---|---|
| `<CODEX_CONTROL_DIR>/CODEX.md` | CODEX.md | `<GITHUB_WORKSPACE>/ai-agent-rules/core` | codex-workspace-rules.md | Codex 工作区执行总规则 | 脱敏后复制 | 抽象本机路径、日志路径和输出目录 |
| `<CODEX_CONTROL_DIR>/runtime-rules.md` | runtime-rules.md | `<GITHUB_WORKSPACE>/ai-agent-rules/core` | codex-workspace-rules.md | Codex runtime 执行边界 | 脱敏合并 | 默认草稿区、blocker、GitHub 同步和脚本边界使用占位符 |
| `<USER_CODEX_CONFIG_DIR>/AGENTS.md` | AGENTS.md | `<GITHUB_WORKSPACE>/ai-agent-rules/core` | user-working-principles-template.md | 用户工作原则模板 | 生成通用模板版 | 保留协作原则，转为通用模板 |
| `<OBSIDIAN_AGENT_RULES_DIR>/任务目标驱动模式验收清单.md` | 任务目标驱动模式验收清单.md | `<GITHUB_WORKSPACE>/ai-agent-rules/core` | task-goal-driven-review-checklist.md | 任务目标驱动验收清单 | 脱敏后复制 | 抽象本机路径和知识库边界 |
| `<CODEX_CONTROL_DIR>/obsidian-write-rules.md` | obsidian-write-rules.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-write-rules.md | Obsidian 写入规则 | 脱敏后复制 | 路径参数化 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-知识库总规则.md` | Obsidian-知识库总规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-knowledge-base-rules.md | Obsidian 知识库总规则 | 脱敏后复制 | 路径和日志模板引用参数化 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-资料组知识化处理流程.md` | Obsidian-资料组知识化处理流程.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-material-knowledge-process.md | 资料组知识化流程 | 复制后补充中文说明 | 保留流程逻辑 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-MOC生成规则.md` | Obsidian-MOC生成规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-moc-generation-rules.md | MOC 生成规则 | 路径参数化后复制 | 输出路径参数化 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-文件命名与分类规则.md` | Obsidian-文件命名与分类规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-file-naming-classification-rules.md | 文件命名与分类规则 | 脱敏后复制 | 测试路径和输出路径参数化 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-智能归档入口规则.md` | Obsidian-智能归档入口规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-smart-archive-entry-rules.md | 智能归档入口规则 | 脱敏后复制 | 路径、日志和输出目录参数化 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-项目笔记生成规则.md` | Obsidian-项目笔记生成规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-project-note-generation-rules.md | 项目笔记生成规则 | 复制后补充中文说明 | 保留规则逻辑 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-测试用例与验收规则.md` | Obsidian-测试用例与验收规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-test-and-acceptance-rules.md | 测试用例与验收规则 | 脱敏后复制 | 测试路径参数化 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-知识卡片生成规则.md` | Obsidian-知识卡片生成规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-knowledge-card-generation-rules.md | 知识卡片生成规则 | 复制后补充中文说明 | 保留规则逻辑 |
| `<OBSIDIAN_AGENT_RULES_DIR>/Obsidian-资料索引生成规则.md` | Obsidian-资料索引生成规则.md | `<GITHUB_WORKSPACE>/ai-agent-rules/agents/obsidian-knowledge-agent/rules` | obsidian-resource-index-generation-rules.md | 资料索引生成规则 | 脱敏后复制 | 输出路径参数化 |
| `<SKILL_DIR>/knowledge-management/SKILL.md` | SKILL.md | `<GITHUB_WORKSPACE>/ai-agent-rules/skills/knowledge-management` | SKILL.md | Knowledge Management Skill 脱敏副本 | 脱敏后复制 | 本机 Skill 如不可写，记录为后续单独任务 |
| `<CODEX_CONTROL_DIR>/directory-map.md` | directory-map.md | `<GITHUB_WORKSPACE>/digital-workspace` | local-folder-map-extended.md | 抽象后的本机目录映射说明 | 抽象化后复制 | 不原样暴露完整本机结构 |

## 同步边界

- GitHub 目标文件只能保留脱敏规则、模板、说明和占位示例。
- 默认草稿和验证输出目录为 `<CODEX_OUTPUT_DIR>`。
- `<KNOWLEDGE_BASE_DIR>/_Codex_Output` 仅作为历史兼容区，不作为默认输出区。
- `<AI_OUTPUT_DIR>` 仅作为临时交付或中转区，不作为长期归档目录。
- commit、push、PR、merge 必须另行确认；Codex 不得自行 merge，不得 force push。
