# Setup Guide

本指南说明如何把本仓库作为脱敏规则模板接入本地 Codex + Obsidian 工作流，并维护本地规则与 GitHub 脱敏副本之间的同步关系。

## 本地目录建议

建议把真实工作区、知识库和 GitHub 脱敏规则仓库分开管理：

```text
workspace/
├── Codex_Control/
├── KnowledgeBase/
├── Codex_Output/
├── AI_Output/
├── source-materials/
└── GitHub/
    └── ai-agent-rules/
```

其中：

- `Codex_Control/` 存放本地执行规则、错误日志和运行记录。
- `KnowledgeBase/` 存放正式 Obsidian 知识库成果。
- `Codex_Output/` 仅用于测试、预览、异常报告、过程检查、备份或用户明确要求的临时输出。
- `AI_Output/` 存放临时交付或中转成果，不作为长期归档目录。
- `source-materials/` 存放待整理或已授权读取的资料。
- `GitHub/ai-agent-rules/` 只存放规则模板和脱敏副本。

不建议把整个工作区初始化为 Git 仓库。真实知识库和 GitHub 脱敏规则仓库应保持分离。

## Obsidian 知识库路径配置

在本地规则中配置以下占位路径：

| 占位符 | 含义 |
|---|---|
| `<WORKSPACE_ROOT>` | 本地工作台根目录 |
| `<CODEX_CONTROL_DIR>` | Codex 控制规则目录 |
| `<CODEX_OUTPUT_DIR>` | 测试、预览、异常报告、过程检查、备份或用户明确要求的临时输出目录 |
| `<AI_OUTPUT_DIR>` | 临时交付或中转成果目录 |
| `<KNOWLEDGE_BASE_DIR>` | 正式 Obsidian / Markdown 知识库目录 |
| `<OBSIDIAN_AGENT_RULES_DIR>` | Obsidian 知识库规则目录 |
| `<RUN_LOG_DIR>` | 运行日志目录 |
| `<GOVERNANCE_ARCHIVE_DIR>` | 治理备份目录 |

公开仓库中应保留占位符，不应写入真实本地绝对路径。

## Codex 规则文件放置方式

推荐把本仓库中的脱敏副本复制到本地规则目录，再按本地环境改写路径：

- `core/codex-workspace-rules.md` -> 本地 Codex 执行总规则。
- `agents/obsidian-knowledge-agent/rules/obsidian-write-rules.md` -> 本地 Obsidian 写入规则。
- `agents/obsidian-knowledge-agent/rules/obsidian-smart-archive-entry-rules.md` -> 本地 Obsidian 智能归档入口规则。
- `agents/obsidian-knowledge-agent/rules/obsidian-knowledge-base-rules.md` -> 本地 Obsidian 知识库总规则。

本地规则可以包含本机路径，但同步回 GitHub 前必须脱敏和参数化。

## 如何使用 source-file-mapping.md

`agents/obsidian-knowledge-agent/source-file-mapping.md` 记录了本地规则文件和 GitHub 脱敏副本之间的映射关系。

使用方式：

1. 修改本地正式规则文件。
2. 根据映射表找到对应的 GitHub 脱敏副本。
3. 手动同步必要规则变更。
4. 把本地路径、日志路径、输出目录替换为占位符。
5. 检查是否包含敏感内容。
6. 通过 draft 分支和 PR 提交。

不要把整个本地规则目录直接复制到 GitHub。

## 如何同步本地规则与 GitHub 脱敏副本

推荐流程：

1. 在本地规则库完成修改和测试。
2. 对照 `source-file-mapping.md` 选择需要同步的脱敏副本文件。
3. 从 GitHub 仓库 `main` 创建 `draft/*` 分支。
4. 只修改映射目标文件。
5. 检查 diff 是否只包含预期文件。
6. 检查是否含有本地绝对路径、用户名、日志、输出目录、密钥或私有资料。
7. 输出 commit 前确认报告，等待用户确认后再 commit。
8. 输出 push 前确认报告，等待用户确认后再 push draft 分支。
9. 输出 PR 前确认报告，等待用户确认后再创建 PR。
10. 人工确认后再合并 `main`，Codex 不得自行合并。

GitHub 只保存规则模板和脱敏副本，不同步正式知识库、运行日志、输出目录、密钥或私有项目资料。

禁止 force push。任何 commit、push、PR、merge 都必须在对应确认节点另行确认。

## 如何处理图片 / 图形占位符

当 Word、PPT、Markdown、汇报材料或方案文档需要图片、架构图、流程图、封面图、场景图、信息图或页面原型示意时，Codex 不直接生成图片。

Codex 只负责：

- 判断是否需要图片或图形。
- 在文档中保留占位符。
- 说明使用位置、表达目的、核心内容、推荐版式和风格要求。
- 输出可复制给其他 AI 图像工具的提示词。

图片实际生成由 ChatGPT Image、image2、Midjourney、即梦、通义万相或其他图像工具完成。

推荐占位格式：

```markdown
【图片 / 图形占位符：名称】

使用位置：

表达目的：

核心内容：

推荐版式：

风格要求：

AI 图片生成提示词：
```

## 如何处理错误日志

本地可以维护错误日志，用于记录 blocker、权限问题、路径问题、命令失败、文件冲突等情况。

错误日志通常包含本机路径、运行上下文和具体错误信息，不应同步到 GitHub 脱敏规则仓库。

同步规则时：

- 不提交真实错误日志。
- 不提交运行日志目录。
- 不提交命令输出中的敏感路径。
- 只在脱敏规则中保留 `<ERROR_LOG_TEMPLATE>` 等占位说明。

## Knowledge Management Skill v1 接入边界

`skills/knowledge-management/SKILL.md` 是工作区级知识管理入口，用于在进入具体 Obsidian / Markdown 知识化动作前，先判断工作区结构、资料来源、输出边界和安全风险。

默认 Skill 安装目录为 `skills/knowledge-management/`。除非需要兼容早期版本，否则不建议安装 `skills/obsidian-project-knowledge-skill/`。

推荐路径变量：

| 变量 | 含义 |
|---|---|
| `<WORKSPACE_ROOT>` | 用户授权的工作区分析起点 |
| `<WORKBENCH_ROOT>` | 日常工作台、控制区和输出区 |
| `<RULES_REPO>` | 规则源码仓库 |
| `<LEGACY_RULES_DIR>` | 旧版稳定规则，只读参照 |
| `<KNOWLEDGE_BASE_DIR>` | 正式 Obsidian / Markdown 知识库目录 |
| `<SOURCE_ARCHIVE>` | 原始资料和最终原始成果归档区 |
| `<CODEX_OUTPUT_DIR>` | 测试、预览、异常报告、过程检查、备份或用户明确要求的临时输出区 |
| `<AI_OUTPUT_DIR>` | 临时交付或中转成果区 |

接入原则：

1. 工作区级任务先只读扫描一级和二级目录。
2. 新版 Skill 开发、测试、覆盖矩阵、验证记录和评价报告应写入规则仓库或用户指定的测试区。
3. Skill 测试阶段不得写入正式 `<KNOWLEDGE_BASE_DIR>`，也不得写入其中的 `_Codex_Output`。
4. 用户授权资料处理且目标目录明确时，正式知识成果默认按 formal knowledge filing 进入对应 `<KNOWLEDGE_BASE_DIR>` 正式目录。
5. 正式知识成果应使用资料类型识别、资料索引、多类型主题笔记、MOC、分型知识卡片、双链、标签、合并去重、版本判断和统一质检体系。
6. 旧版规则目录保持可回退，不在新版验证过程中修改。
7. `<CODEX_OUTPUT_DIR>` 仅用于测试、预览、异常报告、过程检查、备份或用户明确要求的临时输出；`<KNOWLEDGE_BASE_DIR>/_Codex_Output` 仅作为历史兼容区，不作为默认输出区。

## GitHub 分支、PR 和回滚

推荐所有规则修改都走以下流程：

1. 从 `main` 创建 `draft/*` 分支。
2. 修改规则模板或说明文档。
3. 检查 diff 范围。
4. 检查敏感内容。
5. 用户确认后 commit。
6. 用户确认后 push draft 分支。
7. 用户确认后创建 PR。
8. 人工确认后再合并 `main`。

不建议直接提交到 `main`。Codex 不得自行 merge，不得 force push。

回滚方式：

- PR 未合并：关闭 PR 并删除 draft 分支。
- PR 已 squash 合并：新建回滚分支，执行 `git revert <squash_commit_sha>`，再提交回滚 PR。
- PR 已普通 merge：执行 `git revert -m 1 <merge_commit_sha>`，再提交回滚 PR。

## 发布前检查清单

- 是否只修改了预期文件。
- 是否没有真实本地路径。
- 是否没有用户名、密钥、Token、私钥。
- 是否没有正式知识库内容。
- 是否没有运行日志和错误日志。
- 是否没有 `_Codex_Output/` 内容。
- 是否没有客户资料、合同、报价、招采文件或未脱敏业务资料。
- 是否使用 draft 分支和 PR。
