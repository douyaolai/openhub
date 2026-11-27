---
title: VisualLearning
date: 2026-11-27
category: AI教育
type: 网址
source: https://github.com/andrewalumkal/VisualLearning.Skill
tags: [Agent Skill, 可视化讲解, 教育内容, 事实核查]
---

# VisualLearning

## 一句话摘要
> 教 AI agent 把任何主题做成可交互的动画讲解：解说式走读 + 可探索视图，事实逐条对源，出稿前还有审稿 subagent 复查。

## 核心分析与要点

- **核心内容**：一个纯 Markdown 的 agent skill（另附两个示例 HTML），不绑定特定模型或工具。它产出两种互补的形式：**引导式走读**（有解说、分章节、逐步搭出画面，带字幕、进度条、倍速、章节按钮与每步暂停）与**可交互探索器**（同一个模型的多视图切换、下钻、控件与每个元素的白话提示）。两者都跟随系统深浅色。
- **关键亮点 / 结论**：
  - **"每个事实都要对源"是硬约束**：页面上展示的每个事实都要对真实来源核实，并把来源列在页面里。
  - **开工前先让你选方案**：agent 会先提出 2–3 种做法，连同各自查过的来源一起给你，等你选定再动手。
  - **有独立的审稿 subagent**：每完成一部分，另一名 reviewer agent 会核查三个维度——论断是否与来源相符、讲解是否真的教得懂、在浏览器里是否正常；agent 修完并复核后才交付，并报告修了什么。
- **适用场景 / 启发**：把抽象概念（机制、流程、有先后顺序的步骤）做成能"点着看"的讲解页，适合课程素材与产品原理说明。对做教育类 agent 的人，它的三段式（提案 → 构建 → 独立复审）比"一次生成"可靠得多。43 Star，MIT。

## 原文 / 原始资料

原网址：<https://github.com/andrewalumkal/VisualLearning.Skill>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历源码与 Issue。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `andrewalumkal/VisualLearning.Skill` |
| 描述 | 未填写 |
| Star / Fork | 43 / 7 |
| 语言 / 许可 | HTML / MIT |
| 最近推送 | 2026-10-23 |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> It builds two formats that work together:

> Both formats follow the system's light or dark mode.

> The agent needs to read files, search the web and write HTML. A browser it can drive, and the ability to start a subagent, make the checks and reviews stronger.

</details>
