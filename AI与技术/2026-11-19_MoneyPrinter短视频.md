---
title: MoneyPrinter短视频
date: 2026-11-19
category: AI与技术
type: 网址
source: https://github.com/harry0703/MoneyPrinterTurbo
tags: [AI视频, 短视频, TTS, 自动化, LLM]
---

# MoneyPrinter短视频

## 一句话摘要
> 输入主题或关键词，自动生成脚本、匹配素材、加字幕与 BGM、合成高清短视频，14 万 Star 的爆款项目。

## 核心分析与要点

- **核心内容**：以主题/关键词为起点，跑完整条短视频流水线：LLM 写文案 → 素材检索匹配 → TTS 配音 → 字幕 → 背景音乐 → 合成竖屏或横屏成片。
- **关键亮点 / 结论**：
  - 项目定位是「一站式工具」而非框架，UI 与工作流都面向直接产出成片，适合非技术用户。
  - 模型服务可换：README 中可见 Kimi、火山方舟、APIMart 等供应商的接入与赞助说明，说明它把 LLM/TTS/图像都做成了可插拔配置。
  - 14 万 Star 带来的是生态（素材源、模型供应商适配）而非更聪明的算法——本质仍是模板化生产。
- **适用场景 / 启发**：批量铺量型短视频生产；也可作为「多供应商模型编排 + 媒体合成」的工程参考。成片质量高度依赖素材库与文案模型，不适合做需要强创意的品牌片。

## 原文 / 原始资料

原网址：<https://github.com/harry0703/MoneyPrinterTurbo>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `harry0703/MoneyPrinterTurbo` |
| 描述 | 利用 AI 大模型和自动化工作流，根据主题或关键词一键生成高清短视频。Generate HD short videos from a topic or keyword with an automated AI workflow. |
| Star / Fork | 144,633 / 23,247 |
| 语言 / 许可 | Python / MIT |
| 最近推送 | 2026-11-19 |
| 主页 | — |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> - 如果你主要依赖云端 LLM、云端 TTS 和在线素材源，CPU 与内存比 GPU 更重要 - 如果你启用 `faster-whisper`、批量生成或更重的本地处理链路，GPU 会明显提升速度

> 如果你的 AI Agent 支持读取 Skill 文档并操作本地终端，可以直接发送下面这段话。Agent 会自动完成安装、配置和视频生成；只有缺少必要的 API Key 时才会向你询问，完成后会返回生成的视频文件路径。目前支持 macOS 和 Windows。

> 免去本地环境配置，点击直接在 Google Colab 中快速体验 MoneyPrinterTurbo

</details>
