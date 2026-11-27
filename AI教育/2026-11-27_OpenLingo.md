---
title: OpenLingo
date: 2026-11-27
category: AI教育
type: 网址
source: https://github.com/pretzelai/openlingo
tags: [语言学习, AI 家教, 间隔重复, 开源, 多语言]
---

# OpenLingo

## 一句话摘要
> 开源免费的 AI 语言学习平台：AI 对话家教、间隔重复卡片、互动练习与可翻译阅读，支持 15+ 语言，还能一句话生成整个单元。

## 核心分析与要点

- **核心内容**：一个完整的语言学习 Web 应用，四块能力：**AI 对话家教**（用你自己选的 LLM，能按水平调整、跨会话记忆、临场出练习）、**间隔重复（SRS）卡片**、**互动练习**、**带翻译的阅读材料**，另有 TTS/STT 支持听说。
- **关键亮点 / 结论**：
  - **家教能调工具**：`readMemory` / `addMemory` / `rewriteAllMemory` 管理学习者记忆，`srs` 直接查改卡片，`presentExercise` 在对话里内联渲染练习，`createUnit` 从主题生成整单元——这已经超出"聊天机器人"，是能改学习状态的 agent。
  - **一句话生成课程**：README 给的示例是"create a unit about the benefits of open source software in spanish A1 level"，直接产出可访问的单元页。
  - 持久记忆 + SRS 的组合，意味着它能跟踪学习进度，而不是每次从零开始。
- **适用场景 / 启发**：想自建语言学习工具、或想研究"LLM + 记忆 + 间隔重复"三者怎么配合的人。有在线版 openlingo.dev 可直接试。156 Star，MIT，TypeScript。

## 原文 / 原始资料

原网址：<https://github.com/pretzelai/openlingo>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历源码与 Issue。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `pretzelai/openlingo` |
| 描述 | 未填写 |
| Star / Fork | 156 / 33 |
| 语言 / 许可 | TypeScript / MIT |
| 最近推送 | 2026-05-27 |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> A free, open-source, AI-powered language learning platform. Practice through conversations with an AI tutor, interactive exercises, spaced repetition flashcards, and translated reading material — all in 15+ languages.

> Conversational language practice powered by your choice of LLM. The tutor adapts to your level, remembers context across sessions via a persistent memory system, and can generate exercises on the fly.

> The chat tutor has access to tools it can call during conversation:

</details>
