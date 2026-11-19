---
title: Agents-Anywhere
date: 2026-11-19
category: AI与技术
type: 网址
source: https://github.com/anywhere-labs/Agents-Anywhere
tags: [Agent, 远程控制, 跨设备, 自托管]
---

# Agents-Anywhere

## 一句话摘要
> 跨设备 Agent 工作台：在工作电脑上跑 Codex/Claude Code/DSH，用手机、平板或 Web 看会话、回请求、管文件。

## 核心分析与要点

- **核心内容**：在真正干活的工作设备上装桌面客户端（或 Linux 下用 Connector CLI），然后从 macOS/Windows/iOS/Android/Web 任意一端连进来，查看并接管 Codex、Claude Code、DeepSeek Harness 的会话。任务仍在工作设备上执行，客户端只做遥控与展示。
- **关键亮点 / 结论**：
  - 解决了「agent 长任务跑在电脑上，人却离开了」的痛点——手机端可以回复 agent 的请求，不必守着终端。
  - 支持 Cloud 与自托管两种模式；README 说明服务器在中国大陆，国内访问体验更好。
  - 平台覆盖完整，Linux/无图形界面服务器也能通过 Connector 接入。
- **适用场景 / 启发**：远程盯长任务的开发者；把公司机器上的 agent 接到个人手机上。注意 Windows 安装包当前未签名。

## 原文 / 原始资料

原网址：<https://github.com/anywhere-labs/Agents-Anywhere>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `anywhere-labs/Agents-Anywhere` |
| 描述 | 跨设备的开源Agent工作台 |
| Star / Fork | 3,575 / 300 |
| 语言 / 许可 | Python / Apache-2.0 |
| 最近推送 | 2026-11-19 |
| 主页 | https://agents-anywhere.com |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> **Agents Anywhere** 是跨设备的开源 Agent 工作台。连接运行 **Codex、Claude Code 或 DeepSeek Harness** 的工作设备，在桌面、手机和 Web 查看会话、回复请求、管理文件与终端。Agent 在连接的工作设备上执行任务。

> 在工作设备上安装桌面客户端，再通过手机、平板或 Web 访问。Linux 和无图形界面的服务器可使用 Connector CLI 接入。各客户端均可连接 Cloud 或自托管服务。

> **直接使用 Web：** 打开 [web.agents-anywhere.com](https://web.agents-anywhere.com)，注册或登录，开始使用。服务器位于中国大陆，在中国大陆使用可获得最佳体验。

</details>
