# 变更记录

## 2026-06-24
- 同步脱敏版 runtime rules，明确低风险授权范围内可连续执行，高风险任务和 blocker 必须暂停。
- 统一默认草稿区为 `<CODEX_OUTPUT_DIR>`，明确 `<KNOWLEDGE_BASE_DIR>/_Codex_Output` 仅作为历史兼容区。
- 补齐 GitHub 同步边界：commit、push、PR、merge 必须另行确认，Codex 不得自行 merge，禁止 force push。
- 收紧自动化处理口径：优先使用已有工具、一次性命令或内联命令，禁止落盘散乱临时脚本。
- 补充 Knowledge Management Skill 脱敏副本、core 规则、Obsidian 规则、README、setup guide 和映射表的同步说明。

## 2026-06-23
- 新增 `knowledge-management` v1 Skill，作为工作区级知识管理入口。
- 新增工作区目录职责图、旧版能力覆盖矩阵、验证记录和评价报告。
- 更新 README、快速开始和接入指南，明确测试输出不进入正式 KnowledgeBase。
- 本次改造保持旧版 Obsidian 规则只读参照，不修改正式知识库。

## 2026-06-19
- 初始化本地仓库基础目录和说明文件。
- 新增 core 通用规则文件和专项智能体目录。
- 本次未复制现有智能体配置文件，未 push。
- 固化 Codex 调用 GitHub 的后续维护规则：默认使用 `draft/*` 分支，push/PR/merge 前必须确认，敏感信息检查和 dry-run 规则作为长期约束。
- 智能化升级 Codex 调用 GitHub 的维护规则：新增修改类型自动判断、风险等级判断、流程选择、执行前自确认、执行后自检和用户确认简化要求。
