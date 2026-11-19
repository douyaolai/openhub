---
title: AIGCPanel
date: 2026-11-19
category: AI与技术
type: 网址
source: https://github.com/modstart-lib/aigcpanel
tags: [数字人, 声音克隆, TTS, 本地部署, 工作流]
---

# AIGCPanel

## 一句话摘要
> 装在本机的 AI 数字人工作台：口型合成、TTS、声音克隆与 27 个音视频工具全本地跑，显卡不够可切云端。

## 核心分析与要点

- **核心内容**：把数字人生产拆成「AI 模型 / 数字人合成 / 语音处理 / 工具箱 / 可视化工作流」几个工作区，模型只装一次，各页面共用同一份模型列表；同时也支持接云端模型或自备 API。
- **关键亮点 / 结论**：
  - 口型模型可横向比较：MuseTalk、LatentSync、Wav2Lip、Heygem 换着用，方便按效果选型。
  - 七个 TTS 模型 + 6～20 秒参考音频即可复刻音色，覆盖了数字人最刚需的两块能力。
  - 27 个工具里视频类占 16 个（绿幕、字幕、变速、压缩、拼接、自定义 FFmpeg），基本是把 ffmpeg 常用操作做成了图形化。
  - 工作流画布支持 LLM、JS 脚本、MCP 工具调用、条件分支，还能断点续跑；智能直播可接抖音/B站/虎牙/斗鱼/快手弹幕。
- **适用场景 / 启发**：本地化的数字人口播与无人直播；对数据不出本机有要求的团队。VIP 功能（可视化工作流、智能直播）提示了它的商业模式。

## 原文 / 原始资料

原网址：<https://github.com/modstart-lib/aigcpanel>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `modstart-lib/aigcpanel` |
| 描述 | AIGCPanel 是一个简单易用的一站式AI数字人系统，支持视频合成、声音合成、声音克隆，简化本地模型管理、一键导入和使用AI模型。 |
| Star / Fork | 5,809 / 854 |
| 语言 / 许可 | TypeScript / Apache-2.0 |
| 最近推送 | 2026-11-17 |
| 主页 | https://aigcpanel.com/?utm_source=github |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> AIGCPanel 是一个装在自己电脑上的 AI 数字人工作台。模型由你下载到本机，口型合成、语音合成、语音识别、音视频处理都在本地跑；显卡不够用的时候，同一个界面里可以换成云端模型或者你自己的 API。

> 模型在「AI 模型」里装一次就够了，其他页面取的是同一份列表。工作流把口型合成、语音合成、工具箱里的工具都做成节点，前后还能接大模型、JS 脚本和文件操作。

> 上传形象视频，或者给一张正脸照片，让它自己生成 5 秒形象视频。文案交给语音模型合成音轨，也可以直接上传音频。口型模型 MuseTalk、LatentSync、Wav2Lip、Heygem 可以换着比效果，形象模板在「我的形象」里管。

</details>
