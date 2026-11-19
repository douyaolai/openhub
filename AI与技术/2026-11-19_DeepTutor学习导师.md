---
title: DeepTutor学习导师
date: 2026-11-19
category: AI与技术
type: 网址
source: https://github.com/HKUDS/DeepTutor
tags: [AI导师, 多智能体, RAG, Agent, 教育科技, 开源项目]
---

# DeepTutor学习导师

## 一句话摘要
> 港大数据智能实验室（HKUDS）开源的「agent 原生」学习工作台：把对话、出题、研究、沉浸阅读、掌握路径收进同一个可扩展系统，支持多引擎 RAG 知识库、可审计的分层记忆，还能被其他 agent 直接调用。

## 核心分析与要点

- **核心内容**：DeepTutor 不是单一聊天机器人，而是一个把「教、研、创、练」串起来的工作台。八个学习模式（Chat、Quiz、Research、Visualize、Solve、Mastery Path、Reading 等）共享同一份会话上下文，但各自保留专用流程；Home / Learning / Resources 三块按「工作区」组织，Partners 与 Personalization 则跨工作区常驻。技术上以 Python 为后端、Node.js 为前端，提供桌面端（macOS / Windows 预览）、Docker、PyPI、源码四种安装路径；能力以「模块」形式按需安装，例如 `deeptutor[full]` 装完整 Web + CLI，裸 `deeptutor` 只装核心对话与 SDK。

  | 项目 | 值（抓取自仓库页面，2026-11-19） |
  |---|---|
  | 仓库 | `HKUDS/DeepTutor`，Apache-2.0，主语言 Python |
  | 热度 | 60,666 Star / 7,344 Fork / 352 Open Issues |
  | 版本 | 最新 [v1.7.3](https://github.com/HKUDS/DeepTutor/releases/tag/v1.7.3)（2026-11-16） |
  | 时间线 | 创建 2025-12-28，最近更新 2026-11-19 |
  | 论文 | arXiv 2604.26962 |
  | 主题标签 | ai-agents、ai-tutor、deepresearch、multi-agent-systems、rag、interactive-learning 等 |

- **关键亮点 / 结论**：
  - **Agent 原生，可被别的 agent 驱动**。`deeptutor run <capability> "..." --format json` 以 NDJSON 逐行输出事件（`content`、`tool_call`、`tool_result`、`done`），每行带 `session_id`，可串成有状态的多轮；无 TTY 时 `ask_user` 自动以空回复放行，不会挂死。仓库根目录还配了 `SKILL.md` 作为给 agent 的交接文档——这是把「应用」当「工具」设计的典型做法。
  - **记忆是可检查的，不是黑盒**。README 明确分层：L1 traces、L2 facts、L3 synthesis，并可在 Memory Graph 里顺着证据链接审计。相比常见的「向量库塞一堆历史」，这更像可追溯的档案。
  - **检索引擎可选且可评测**。知识库可按 KB 绑定 LlamaIndex（默认混合向量 + BM25）、PageIndex、GraphRAG、LightRAG、WeKnora、Tencent IMA、MarginNote 4、Kiwix、Obsidian 等；`deeptutor kb eval` 用自建 QA 集算 Recall@k / Precision@k / nDCG@k / MRR / MAP / Hit@k，`kb eval-diff` 对比两次报告。注意：这是**评测工具**，README 未提供该项目的效果基准数据。
  - **技能生态走开放格式**。技能即「一个含 `SKILL.md` 的文件夹」（YAML frontmatter + Markdown），不绑定 DeepTutor，因此 EduHub、ClawHub 都能当源。导入统一过安全闸：查注册表安全结论、防路径穿越/压缩炸弹/符号链接、剥离可执行位、强制去掉 `always:`（避免技能把自己塞进每次系统提示）、写 `.hub-lock.json` 留痕。
  - **模块化安装是 1.7 的主要变化**。README 专门给了从 1.6.15 及更早版本升级的迁移说明（先停服务、备份 runtime home、卸掉旧的 `deeptutor-cli` 包、保持同一 `DEEPTUTOR_HOME`）。

- **适用场景 / 启发**：
  - **自建个人学习系统**：把教材、论文、笔记灌进知识库，用 Book 生成结构化「活书」，用 Mastery Path 拆知识点，用 Immersive Reading 边读边问——适合有大量 PDF/EPUB 需要消化的人。
  - **教育产品的架构参考**：它的分层（会话上下文 / 知识库 / 记忆 / 技能 / 伙伴）与「同一 runtime 多模式」的设计，比单纯套一层 prompt 的 AI 家教更接近可长期演进的结构。
  - **Agent 工具化的范式**：CLI 双模（人用 REPL / 机器用 JSON）+ 状态化 session + SKILL.md 交接，是「让 AI 应用成为另一个 AI 的工具」的完整样例。
  - **注意**：README 以功能与使用说明为主，未给出基准测试、准确率或成本数据；Star 数极高（6 万+），但热度不等于效果，实际选型仍建议本地跑通再评估。

## 原文 / 原始资料

原网址：<https://github.com/HKUDS/DeepTutor>

> 抓取说明：按仓库类链接规则，仅取 `README.md` 与仓库元数据，未遍历文件树、源码、Issue、PR、Commit。`raw.githubusercontent.com` 在本网络被重置，改由 GitHub Contents API 取得同一份 README 原文（92,447 字符）。

<details>
<summary>展开查看：README 关键摘录（逐字照录）</summary>

**定位**

> DeepTutor is an agent-native learning workspace that connects tutoring, research, creation, and practice in one extensible system.

**六项核心能力（Key Features 原文条目）**

> - **One runtime, many learning modes** — Chat, Quiz, Research, Visualize, Solve, Mastery Path, Reading, and more share session context while retaining purpose-built workflows.

> - **A connected learning workspace** — Home, Learning, and Resources connect Chat, Books, Reading, Practice, Task Board, Calendar, and Learning notebook with shared materials, progress, and learning context.

> - **Grounded knowledge and reading** — Build versioned libraries with LlamaIndex, PageIndex, GraphRAG, or LightRAG, connect external knowledge sources, and learn beside documents, video, and audio with source-linked citations.

> - **Inspectable memory** — L1 traces, L2 facts, and L3 synthesis make personalization visible and editable, with evidence links you can audit in the Memory Graph.

> - **Extensible by design** — Add personas, built-in or community skills, MCP services, CLI apps, and generation models through one agent-native runtime.

**Docker 快速试跑**

```bash
docker run --rm --name deeptutor \
  -p 127.0.0.1:3782:3782 \
  -v deeptutor-data:/app/data \
  ghcr.io/hkuds/deeptutor:latest
```

**CLI 的两种用法**

> One `deeptutor` binary, two ways in: an interactive **REPL** for people who live in the terminal, and structured **JSON** for other agents that drive DeepTutor as a tool. Same capabilities, tools, and knowledge bases either way.

> DeepTutor is built to be *operated by another agent*. Add `--format json` to any `run` and each turn streams **NDJSON — one event per line** (`content`, `tool_call`, `tool_result`, `done`, …), every line tagged with its `session_id`. Runs are headless-safe: an `ask_user` pause with no TTY auto-resolves with an empty reply instead of hanging.

**技能导入的安全闸（原文条目）**

> - archives are extracted defensively with path-traversal, entry-count, size, compression-ratio, suffix, and symlink checks; executable bits are stripped, while extensionless files remain allowed;

> - frontmatter is normalized to DeepTutor's schema and `always:` is **stripped**, so a downloaded skill can never force itself into every system prompt;

**项目性质**

> DeepTutor is an open-source project led by [Bingxi Zhao](https://github.com/pancacake) within the [HKUDS](https://github.com/HKUDS) Group, and it iterates in a **fully open-source form**, built together with the community. So far, we **DO NOT** have paid online products of any form.

</details>

<details>
<summary>展开查看：安装方式与版本对照</summary>

| 方式 | 适合谁 | 关键命令 / 说明 |
|---|---|---|
| 桌面端（预览） | 不想装运行时 | macOS Apple Silicon / macOS Intel 的 DMG、Windows x64 的 Setup `.exe`；Windows 预览版未签名，可能有 SmartScreen 提示 |
| Docker | 最快试全功能 | 见上方 `docker run`，默认 `http://127.0.0.1:3782`，数据存命名卷 |
| PyPI | 想用完整 Web + CLI | 需 Python 3.11–3.14、Node.js 20.9+；`pip install -U "deeptutor[full]"` → `deeptutor init` → `deeptutor start` |
| 源码 | 贡献者 / 追 dev | 需 Python 3.11–3.14、Node.js 22 LTS；克隆 `dev` 分支，`pip install -r requirements/full.txt`，`cd web && npm ci`，`deeptutor start --dev` |
| 纯 CLI | 只想要终端 | `pip install -U deeptutor` → `deeptutor init --cli` → `deeptutor chat`；无需 Node.js |

- 运行时的私有设置位于启动目录下的 `data/user/settings/`，或由 `DEEPTUTOR_HOME` / `deeptutor start --home` 指定。
- 从 1.6.15 或更早升级：停服务 → 备份 runtime home → 卸载旧的 `deeptutor-cli` → 安装新包 → 保持同一 `DEEPTUTOR_HOME` → `python -m pip check`、`deeptutor module list`。

</details>
