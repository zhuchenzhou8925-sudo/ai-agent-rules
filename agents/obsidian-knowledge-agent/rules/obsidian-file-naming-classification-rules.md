<!-- Public sanitized copy. Replace placeholders such as <WORKSPACE_ROOT> and <KNOWLEDGE_BASE_DIR> with local paths before private use. Do not publish real client, project, contract, quote, contact, or source-path data. -->

# Obsidian 文件命名与分类规则

# 文件用途

本文件用于统一 Obsidian 相关正式知识成果、临时输出、测试文件、资料索引、多类型主题笔记、MOC 和知识卡片的命名与分类。

# 适用范围

适用于经用户授权写入正式 KnowledgeBase 的 Markdown 知识成果，以及 `<CODEX_OUTPUT_DIR>`、`<CODEX_OUTPUT_DIR>/_Test/` 中的测试、预览、异常报告、过程检查、备份或用户明确要求的临时输出。`KnowledgeBase/_Codex_Output` 仅作为历史兼容说明，不再作为默认输出区。

# 输入要求

- 必须明确文件类型。
- 必须明确主题或项目名称。
- 必须明确生成日期。
- 必须明确是否为测试文件。

# 输出要求

文件名应简洁、稳定、可检索，不使用“临时”“新文件”“资料整理”等空泛名称。

# frontmatter 要求

frontmatter 中的 `title` 应与文件名主题一致，`type` 应与文件类型一致。正式知识成果 `status` 应为 `reviewed`；测试、预览或临时输出可使用 `draft`。

# 正文结构要求

正文标题应与 `title` 保持一致。测试文件必须在正文中说明“测试状态说明”。

# 双链与标签要求

- 双链使用不带后缀的文件主题名。
- 标签优先使用中文业务标签。
- 测试文件必须包含 `#测试`。

# 目录归属规则

| 类型 | 命名格式 | 默认目录 |
|---|---|---|
| MOC | `主题名称-MOC-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 资料索引 | `主题名称-资料索引-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 项目笔记 | `项目名称-项目笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 研究笔记 | `主题名称-研究笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 文献笔记 | `文献主题-文献笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 技术笔记 | `技术对象-技术笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 产品笔记 | `产品名称-产品笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 政策标准笔记 | `政策或标准名称-政策标准笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 商务笔记 | `商务事项-商务笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 方法笔记 | `方法名称-方法笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 未来扩展主题笔记 | `主题名称-扩展笔记-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 知识卡片 | `知识点名称-知识卡片-YYYYMMDD.md` | 授权正式目录；临时用途为 `_Codex_Output` |
| 测试输入 | `test-用途-编号.md` | `<CODEX_OUTPUT_DIR>/_Test/input` |
| 测试输出 | `test-类型.md` | `<CODEX_OUTPUT_DIR>/_Test/output` |
| 测试报告 | `Obsidian-规则闭环测试报告.md` | `<CODEX_OUTPUT_DIR>/_Test/report` |

# 禁止事项

- 禁止使用含糊文件名。
- 禁止直接使用外部资料原文件名作为知识库文件名。
- 禁止批量重命名正式文件。
- 禁止覆盖已有文件。
- 禁止将测试文件命名为正式成果文件。

# 自检清单

| 检查项 | 要求 |
|---|---|
| 文件名 | 清晰、稳定、可检索 |
| 日期 | 正式成果和临时输出建议带日期 |
| 类型 | 与内容一致 |
| 测试标识 | 测试文件必须明确 |
| 目录 | 符合授权范围；正式成果进入正式目录，临时用途进入 `_Codex_Output` |

# 测试样例要求

测试文件使用固定名称，便于重复检查：`test-project-material-001.md`、`test-project-note.md` 等。

# 验收标准

- 文件名能判断内容类型和用途。
- 文件目录符合授权范围。
- 测试文件不会与正式知识库文件混淆。
