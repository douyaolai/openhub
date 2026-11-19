---
title: Pixelle-Video
date: 2026-11-19
category: AI与技术
type: 网址
source: https://github.com/ATH-MaaS/Pixelle-Video
tags: [AI视频, 短视频, ComfyUI, AIGC, TTS]
---

# Pixelle-Video

## 一句话摘要
> 给一个主题就自动出成片：写文案、配图、配音、加 BGM、合成一气呵成，底层是 ComfyUI 工作流，30k Star。

## 核心分析与要点

- **核心内容**：输入「主题」或固定脚本，管线依次完成文案撰写 → AI 配图/视频 → TTS 语音 → 背景音乐 → 视频合成，目标用户是零剪辑经验的人。WebUI 内可配置图像、视频、TTS 三类模型供应商（含 Base URL 与代理开关），也支持调用 RunningHub 的云端显卡，本地算力不够时不必自己堆机器。
- **关键亮点 / 结论**：
  - 把 ComfyUI 工作流包装成了产品：用户看到的是「主题进、成片出」，而不是一张节点图。
  - 扩展模块已覆盖数字人口播、图生视频、动作迁移，说明它从"图文拼接"往"有人出镜"的方向扩。
  - 提供 Windows 一键整合包，显著降低非开发者门槛；macOS/Linux 走源码安装。
- **适用场景 / 启发**：口播号、影视解说、批量短视频铺量的生产工具；也可作为「把 ComfyUI 封装成 C 端产品」的参考实现。需要注意的是它强依赖模型环境与工作流模板，实际产出质量取决于所配模型。

## 原文 / 原始资料

原网址：<https://github.com/ATH-MaaS/Pixelle-Video>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `ATH-MaaS/Pixelle-Video` |
| 描述 | 🚀 AI 全自动短视频引擎 ｜ AI Fully Automated Short Video Engine |
| Star / Fork | 30,255 / 4,392 |
| 语言 / 许可 | Python / Apache-2.0 |
| 最近推送 | 2026-06-14 |
| 主页 | https://aidc-ai.github.io/Pixelle-Video/zh |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> 从输入文本到最终视频输出，整个流程简洁清晰：**文案生成 → 配图规划 → 逐帧处理 → 视频合成**

> 每个环节都支持灵活定制，可选择不同的 AI 模型、音频引擎、视觉风格等，满足个性化创作需求。

> 以下是使用 Pixelle-Video 生成的实际案例，展示了不同主题和风格的视频效果：

</details>
