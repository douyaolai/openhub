---
title: motionforge
date: 2026-11-25
category: 产品与商业
type: 网址
source: https://github.com/aykutucesai/motionforge
tags: [动效设计, 视频生成, Coding Agent, three.js]
---

# motionforge

## 一句话摘要
> 给 coding agent 用的开源动效设计工具包：说一句要什么视频，它自己写脚本、卡配音时间、搭 2D/3D 场景、渲染，还先自查一遍。

## 核心分析与要点

- **核心内容**：Motionforge 把"做动态设计视频"整个交给编码 agent。你描述视频，agent 负责写钩子与脚本、把每个词对齐到配音、搭 2D 与 3D 场景、渲染，并在交付前自检。仓库自带 **100 种风格、20 个分类**（创作者、电商、房产、足球、纪录片、教育、科技、金融、美食等），每种风格都是一份完整规格：配色、字体、版式、动效、剪辑节奏、音效与标志性镜头。
- **关键亮点 / 结论**：
  - **3D 场景用 three.js 写成代码**：产品转台、带航线的地球、带步行距离圈的城市、自动搭建的房子、足球战术板、3D 图表，全部确定性渲染、可离线跑——不依赖生成式视频模型。
  - **"先自检再交付"是它和多数 AI 视频工具的差别**：agent 会检查自己的产出，而不是把半成品直接丢给用户。
  - 支持 Claude Code 插件安装，也适配 Codex、Cursor 等 agent。
- **适用场景 / 启发**：电商、课程、房产这类需要"稳定出片 + 统一视觉"的场景；对做 agent 工具的人，它是一个"风格规格库 + 渲染管线"打包成 skill 的样本。MIT 许可，173 Star，偏新项目，成片质量取决于 agent 与素材。

## 原文 / 原始资料

原网址：<https://github.com/aykutucesai/motionforge>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `aykutucesai/motionforge` |
| 描述 | Open-source AI motion design toolkit for coding agents |
| Star / Fork | 173 / 24 |
| 语言 / 许可 | HTML / MIT |
| 最近推送 | 2026-11-03 |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> **Motion design videos, written in code by your coding agent.**

> Describe the video. Your agent writes the hook and script, times every word to the voice-over, builds 2D and 3D scenes, renders, and checks its own work before you see it.

> motionforge turns that into a checked MP4 through fixed stages:

</details>
