# ai-agent-rules
中文名称：AI 智能体规则与提示词仓库。

## 1. 仓库用途
用于管理 Codex、Obsidian、PPT、招采、项目管理等智能体规则、提示词、模板、执行边界和自检规则。

## 2. 适合存放的内容
- 智能体通用执行规则
- Codex 使用规则
- 各专项智能体规则
- 提示词模板
- 脱敏输入输出样例
- 任务验收清单

## 3. 不允许存放的内容
- 客户资料、合同、报价、招采文件
- 内部敏感资料、未脱敏业务资料
- `.env`、API Key、Token、密码、SSH 私钥
- Obsidian 正式知识库全文
- `_Codex_Output/` 未筛选内容

## 4. 目录说明
| 英文目录/文件 | 中文说明 | 用途 |
|---|---|---|
| README.md | 仓库说明 | 说明本仓库定位和使用规则 |
| CODEX.md | Codex 执行入口规则 | Codex 读取本仓库时优先参考 |
| core/ | 通用核心规则 | 存放所有智能体共用规则 |
| core/execution-rules.md | 执行规则 | 说明智能体执行边界 |
| core/github-workflow-rules.md | GitHub 工作流规则 | 管理分支、push、PR 和确认流程 |
| core/file-safety-rules.md | 文件安全规则 | 管理敏感文件排除和自检 |
| core/blocker-rules.md | 阻塞处理规则 | 说明不确定或高风险场景如何暂停 |
| core/task-review-checklist.md | 任务复核清单 | 提交或上传前自检 |
| agents/ | 专项智能体规则 | 存放不同业务智能体 |
| agents/obsidian-knowledge-agent/ | Obsidian 知识库智能体 | 管理 Obsidian 入库、MOC、项目笔记、知识卡片规则 |
| agents/ppt-report-agent/ | PPT 与汇报材料智能体 | 管理 PPT 大纲、排版、汇报材料规则 |
| agents/bidding-agent/ | 招采、报价、任务书智能体 | 管理招采、报价、任务书、评审标准规则 |
| agents/project-management-agent/ | 项目管理与需求分析智能体 | 管理需求拆解、技术路径、实施计划规则 |
| examples/ | 脱敏样例 | 只允许放脱敏输入输出样例 |
| changelog.md | 变更记录 | 记录仓库更新 |

## 5. Codex 使用规则
Codex 可以在用户确认后维护本仓库。复制任何现有规则前，必须先输出候选清单、映射表和敏感信息检查结果。

## 6. 跨设备使用说明
新设备 clone 本仓库后，可恢复智能体规则目录和提示词模板索引；真实业务资料不随仓库同步。

## 7. 变更记录
详见 `changelog.md`。
