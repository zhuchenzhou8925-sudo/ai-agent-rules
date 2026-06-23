# ai-agent-rules

AI 智能体规则与提示词仓库。

## 项目定位

这是一个基于 Codex + Obsidian 的项目型知识库智能体规则模板，用于项目资料整理、知识卡片生成、MOC 挂接、资料索引、文档输出和汇报材料辅助生成。

## 这是什么

本仓库存放一组经过脱敏整理的智能体规则、提示词模板、执行边界、文件安全规则和知识库工作流说明。它适合被复制到本地 Codex、Obsidian 或类似本地文件处理智能体环境中，作为项目资料知识化处理的规则基础。

核心目标是让智能体在处理资料前先理解任务目标，先只读扫描和建立清单，再按项目笔记、资料索引、MOC、知识卡片和文档输出等路径组织成果。

## 这不是什么

- 不是完整软件产品。
- 不是 Obsidian 插件。
- 不包含用户的私有知识库内容。
- 不包含客户资料、合同、报价、招采文件或未脱敏业务资料。
- 不替代人工复核、业务确认和正式发布审批。
- 不建议直接接入包含敏感资料的目录；使用前应先确认权限、范围和脱敏策略。

## 适用对象

- 使用 Obsidian 管理项目资料、方案资料、知识卡片和 MOC 的个人或团队。
- 需要用 Codex 或类似本地文件处理智能体整理资料的人。
- 从事项目管理、数字化方案、智慧工地、BIM、数字孪生、AI 应用、招采支持、汇报材料整理的人。
- 希望把零散资料沉淀为可复用知识库结构的团队。

## 核心能力

- 只读扫描资料目录并生成文件清单。
- 按项目资料、产品能力、行业场景、商务资料、汇报材料、可复用知识分类。
- 生成项目笔记、资料笔记、知识卡片、资料索引和 MOC。
- 建立双链、标签和上层 MOC 挂接建议。
- 辅助生成 Word、PPT、Markdown、汇报材料和方案文档结构。
- 对图片、架构图、流程图、封面图、场景图等内容，只保留占位符、说明和 AI 图片生成提示词。
- 通过 draft 分支、PR 和人工确认维护脱敏规则副本。

## 仓库结构

| 路径 | 用途 |
|---|---|
| `CODEX.md` | Codex 读取本仓库时的入口规则 |
| `core/` | 通用执行、安全、GitHub 工作流和复核规则 |
| `agents/obsidian-knowledge-agent/` | Obsidian 知识库智能体规则 |
| `agents/ppt-report-agent/` | PPT 与汇报材料智能体规则 |
| `agents/bidding-agent/` | 招采、报价、任务书相关规则 |
| `agents/project-management-agent/` | 项目管理与需求分析规则 |
| `skills/` | 可复制到 AI 助手或项目环境中的轻量级 Skill |
| `docs/first-use-guide.md` | 第一次使用指南 |
| `docs/quick-start.md` | 最小使用流程 |
| `docs/setup-guide.md` | 本地接入和同步指南 |
| `docs/example-vault-structure.md` | 推荐 Obsidian 知识库目录结构 |
| `examples/` | 脱敏输入输出样例占位 |
| `changelog.md` | 仓库变更记录 |

## 可用 Skill

- [Knowledge Management Skill v1](skills/knowledge-management/SKILL.md)：用于从工作区级视角进行只读目录分析、资料分类、Obsidian / Markdown 知识化规划、资料索引、项目笔记、MOC、知识卡片、双链、标签和迁移建议。v1 测试输出不进入正式 KnowledgeBase。
- [Obsidian 项目型知识库整理 Skill](skills/obsidian-project-knowledge-skill/SKILL.md)：用于让 AI 助手、Codex、ChatGPT Project 或类似智能体读取工作流说明，把项目文件、方案材料、商务资料、行业内容和汇报材料整理成可维护的 Obsidian 知识库。

配套示例与模板：

- [工作区目录职责图模板](skills/knowledge-management/templates/workspace-directory-map-template.md)
- [旧版能力覆盖矩阵模板](skills/knowledge-management/templates/legacy-coverage-matrix-template.md)
- [输入目录扫描示例](skills/obsidian-project-knowledge-skill/examples/input-folder-example.md)
- [入库输出示例](skills/obsidian-project-knowledge-skill/examples/archive-output-example.md)
- [文档输出占位示例](skills/obsidian-project-knowledge-skill/examples/document-output-example.md)
- [知识卡片模板](skills/obsidian-project-knowledge-skill/templates/knowledge-card-template.md)
- [项目笔记模板](skills/obsidian-project-knowledge-skill/templates/project-note-template.md)
- [MOC 模板](skills/obsidian-project-knowledge-skill/templates/moc-template.md)
- [图片 / 图形占位符模板](skills/obsidian-project-knowledge-skill/templates/image-placeholder-template.md)

## 快速开始

建议先阅读：

1. [第一次使用指南](docs/first-use-guide.md)
2. [快速开始](docs/quick-start.md)
3. [本地接入指南](docs/setup-guide.md)
4. [推荐 Obsidian 知识库结构](docs/example-vault-structure.md)

最小流程：

1. 准备一个 Obsidian 知识库。
2. 准备 Codex 或类似本地文件处理智能体。
3. 复制本仓库中的规则模板。
4. 按本地目录结构配置路径。
5. 对待整理资料先执行只读扫描。
6. 人工确认分类、入库和迁移建议。
7. 再执行知识卡片、项目笔记、资料索引或 MOC 生成。

## 使用前提

- 使用者需要具备一个本地 Obsidian 知识库或等价 Markdown 知识库。
- 使用者需要根据自己的本地目录和 Obsidian 库结构调整路径。
- 使用者需要明确哪些资料允许被智能体读取、整理或入库。
- 使用者需要自行维护隐私、权限、脱敏和备份策略。
- 若要同步到 GitHub，只同步规则模板和脱敏副本，不同步真实知识库内容。

## 安全边界

- 第一次处理资料必须只读扫描。
- 工作区级分析先只扫描一级和二级目录，除非任务需要并经说明后再进入更深层材料。
- 不直接移动、删除、重命名原始文件。
- 不把整个工作区初始化为 Git 仓库。
- 不同步正式知识库、运行日志、输出目录、密钥或私有项目资料。
- 不把未脱敏客户资料、合同、报价、招采文件提交到 GitHub。
- Skill 开发和验证材料应留在规则仓库或用户指定的测试输出区，不写入正式 KnowledgeBase 或 KnowledgeBase 内的 `_Codex_Output`。
- 图片类内容不由 Codex 生成；Codex 只保留图片 / 图形占位符、说明和 AI 图片生成提示词。
- 正式入库、对外发布、业务口径、敏感案例和具体承诺必须人工确认。

## 典型应用场景

- 整理项目资料包，生成资料索引和项目笔记。
- 把方案、汇报、可研、会议纪要拆解为可复用知识卡片。
- 建立主题 MOC，把项目笔记、资料索引和知识卡片挂接起来。
- 基于知识库生成 PPT 大纲、页面内容、Word 报告或 Markdown 汇报材料。
- 为架构图、流程图、封面图和场景图生成占位说明和 AI 图片提示词。
- 管理脱敏规则副本，并通过 GitHub PR 审核后同步更新。

## 后续扩展方向

- 补充更多脱敏输入输出样例。
- 增加不同行业的知识库模板。
- 增加 PPT、招采、报价、项目管理等专项规则示例。
- 增加规则同步检查清单。
- 增加团队协作、版本管理和审计流程说明。
