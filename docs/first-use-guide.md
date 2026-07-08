# 第一次使用指南：用 AI 整理一个项目资料文件夹

本指南面向第一次接触本仓库的用户，帮助你用一个最小案例跑通 Obsidian / Markdown 知识库整理 Skill。

这不是测试文件、测试脚本、测试用例或自动化验收文件，而是一份上手教程。目标是让你理解：如何让 AI 助手读取 Skill，如何先只读扫描资料，如何确认方案，再按 formal knowledge filing 生成资料索引、多类型主题笔记、MOC 和分型知识卡片。

## 适用前提

开始前请确认：

- 你已经有一个 Obsidian 知识库，或准备使用一个 Markdown 文件夹模拟知识库。
- 你已经有一个能够读取本地文件并生成 Markdown 的 AI 助手，例如 Codex、ChatGPT Project、Claude Code 或类似工具。
- 你准备的资料已经获得授权，可以被 AI 助手读取。
- 你不会把真实客户资料、合同、报价、密钥、运行日志或正式知识库内容提交到公开仓库。

## 你将跑通什么

本指南会用一个小型资料夹完成一次完整流程：

1. 让 AI 助手读取 Skill。
2. 对资料夹执行只读扫描。
3. 获得文件清单、分类建议和入库方案。
4. 人工确认处理方案。
5. 生成资料索引、主题笔记、MOC 挂接和具备复用价值的知识卡片。
6. 人工复核后，再决定是否写入或保留在正式 Obsidian / Markdown 知识库。

## 准备一个最小资料夹

建议先准备一个低风险、已脱敏的小资料夹，例如：

```text
example-project-materials/
├── project-brief.md
├── solution-outline.md
├── meeting-notes.md
└── report-draft.md
```

如果你还没有真实资料，可以先用几份自写的示例 Markdown 文件代替。第一次使用不建议直接接入完整历史资料库，也不建议接入包含客户、合同、报价、招采、账号或密钥的目录。

## 准备 Obsidian 知识库结构

你可以先准备一个简化版知识库结构：

```text
KnowledgeBase/
├── 01_项目资料/
├── 06_可复用知识/
├── 07_MOC/
└── 08_资料索引/
```

第一次跑通时，如只是测试或预览，可以先把 AI 输出放在单独的临时 Markdown 文件夹中。用户授权正式入档且目标目录明确时，应直接按正式知识类型写入对应知识库目录，而不是默认采用草稿迁移流程。

## 让 AI 助手读取 Skill

将以下 Skill 提供给 AI 助手读取：

```text
skills/knowledge-management/SKILL.md
```

第一次使用时，只需要复制或安装 `skills/knowledge-management/`。不要同时安装两个 Obsidian 知识库相关 Skill。

注意：这个 Skill 是给 AI 助手读取的工作流说明，不是可直接运行的终端程序。不要在终端里执行 `run skill` 之类命令。

正确做法是对 AI 助手说：

```text
请读取 skills/knowledge-management/SKILL.md，并按其中的工作流帮我整理一个资料文件夹。第一次只做只读扫描，不要移动、删除、重命名或写入正式知识库。
```

## 第一步：只读扫描资料夹

给 AI 助手一个已授权的资料夹，并明确只读边界：

```text
请只读扫描 example-project-materials/，输出文件清单、资料类型识别、主题笔记类型建议和建议生成的 Obsidian 笔记类型。

要求：
1. 不移动、删除、重命名任何文件。
2. 不写入正式 Obsidian 知识库。
3. 先判断这些资料应如何入库，而不是判断它们有没有价值。
4. 输出资料索引、多类型主题笔记、MOC 和分型知识卡片的建议。
```

AI 助手应先输出类似内容：

```markdown
## Scan Result

- Scope: `example-project-materials/`
- Mode: read-only scan
- File count:
- Main categories:
- Possible duplicates:
- Suggested outputs:
- Blockers:
- Next confirmation needed:
```

如果 AI 助手试图直接移动文件、改名、归档或写入正式知识库，请停止并要求它回到只读扫描流程。

## 第二步：确认入库方案

阅读 AI 助手给出的建议，重点确认：

- 是否需要生成项目、研究、技术、产品、政策标准、商务、方法或扩展主题笔记。
- 是否需要生成资料索引。
- 是否需要建立项目 MOC。
- 哪些内容适合拆成知识卡片。
- 哪些内容需要脱敏、标注不确定或等待人工确认。
- 如果只是测试或预览，临时输出应放在哪里；如果是正式入档，目标知识库目录是否明确。

可以这样回复：

```text
确认这是测试预览，先生成临时预览，不写入正式知识库。

请基于扫描结果生成：
1. 一个主题笔记预览；
2. 一个资料索引预览；
3. 一个 MOC 挂接建议；
4. 2-3 张可复用知识卡片预览。

请保留来源说明，并标注需要人工复核的内容。
```

## 第三步：生成 Obsidian 预览或正式成果

AI 助手生成预览或正式成果时，可以参考这些模板：

- `skills/knowledge-management/templates/`
- `skills/knowledge-management/references/`

一个合格的知识成果应包含：

- 项目背景、资料来源和核心判断。
- 资料索引，包括文件名、类别、摘要、关键词和复用方向。
- MOC 链接建议。
- 知识卡片，每张只表达一个可复用概念、方法或观点。
- 不确定事项和人工复核项。

## 第四步：处理需要图片或图形的内容

如果你要求 AI 助手基于知识库生成 Word、PPT 或 Markdown 文档，且文档需要封面图、架构图、流程图、场景图或信息图，AI 助手不应直接生成图片。

正确输出方式是保留图片 / 图形占位符，例如：

```markdown
【Image / Diagram Placeholder: Application architecture diagram】

Usage position:
Slide 3 main content area.

Expression purpose:
Explain how source materials, project notes, knowledge cards, MOC, and document outputs connect.

Core content:
Source files, resource index, project notes, knowledge cards, MOC, human review, and final report outputs.

Recommended layout:
Layered architecture diagram.

Style requirements:
Clean, professional, suitable for formal presentation.

AI image prompt:
Create a clean 16:9 layered architecture diagram showing source materials flowing into resource index, project notes, knowledge cards, MOC, human review, and final document outputs. Use professional blue, gray, and white colors. No real company names or sensitive data.
```

图片实际生成应交给 ChatGPT Image、image2、Midjourney、即梦、通义万相或其他图像工具完成。AI 助手不得因为无法生成图片而中断 Word、PPT 或 Markdown 文档输出。

## 第五步：人工复核后再正式入档或复用

在把测试预览写入正式 Obsidian 知识库前，或在正式成果对外复用前，请人工检查：

- 来源是否保留。
- 是否存在敏感内容。
- 是否有未验证事实。
- 项目事实和可复用观点是否区分清楚。
- MOC、标签和双链是否合理。
- 是否需要继续拆分知识卡片。

确认无误后，如果用户授权正式入档且目录明确，可将正式知识成果写入对应目录，例如：

```text
KnowledgeBase/
├── 01_项目资料/
├── 06_可复用知识/
├── 07_MOC/
└── 08_资料索引/
```

## 常见错误

- 一开始就让 AI 助手整理完整历史资料库。
- 没有只读扫描，直接要求移动、删除或重命名文件。
- 把入库理解成只生成知识卡片，忽略项目笔记、资料索引和 MOC。
- 把正式知识库、运行日志、输出目录或私有资料同步到公开仓库。
- 要求 Codex 或 AI 助手直接生成图片，而不是输出占位符和图片生成提示词。

## 下一步

跑通这个最小案例后，可以继续阅读：

- [快速开始](quick-start.md)
- [本地接入指南](setup-guide.md)
- [推荐 Obsidian 知识库结构](example-vault-structure.md)
- [Knowledge Management Skill](../skills/knowledge-management/SKILL.md)
