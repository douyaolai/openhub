---
title: LiveTalking
date: 2026-11-19
category: AI与技术
type: 网址
source: https://github.com/lipku/LiveTalking
tags: [数字人, 实时流, TTS, 直播]
---

# LiveTalking

## 一句话摘要
> 实时交互流式数字人引擎：文本或语音驱动虚拟人说话，支持打断、全身拼接与 WebRTC/RTMP 输出，已在业内广泛商用。

## 核心分析与要点

- **核心内容**：一个实时数字人引擎，把 TTS、口型驱动与视频流串起来，支持 WebRTC、RTMP 与虚拟摄像头输出，可对接前端 API 做自己的界面。
- **关键亮点 / 结论**：
  - 模型覆盖广：ernerf、musetalk、wav2lip、Ultralight-Digital-Human 都能跑，可按算力与效果取舍。
  - 交互细节齐全：支持数字人说话被打断、不说话时播放自定义动作视频、全身视频拼接、多并发。
  - 场景清单直接对应商业用途：24 小时无人直播带货、数字人客服、在线教育、大屏讲解、短视频批量出镜。
- **适用场景 / 启发**：需要"能对话的数字人"而非"生成一段视频"的场景。部署上依赖 GPU 与模型权重，实时性对硬件要求较高。

## 原文 / 原始资料

原网址：<https://github.com/lipku/LiveTalking>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `lipku/LiveTalking` |
| 描述 | Real time interactive streaming digital human |
| Star / Fork | 10,507 / 1,687 |
| 语言 / 许可 | Python / Apache-2.0 |
| 最近推送 | 2026-10-20 |
| 主页 | https://www.livetalking.ai |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> LiveTalking 基于实时流式数字人技术，通过文本或语音驱动虚拟形象说话，结合 LLM 实现智能对话。适用于以下场景：

> **核心流程**：用户输入文字/音频 → LLM 生成回复（可选）→ TTS 合成语音 → 数字人实时口型同步 → 音视频推流输出

> 已在 Ubuntu 22.04、Python 3.12、PyTorch 2.9.1、CUDA 12.8 测试通过。

</details>
