---
title: wechatbot
date: 2026-11-19
category: 开发与运维
type: 网址
source: https://github.com/corespeed-io/wechatbot
tags: [微信, SDK, Bot, 多语言]
---

# wechatbot

## 一句话摘要
> 微信 iLink Bot SDK：Node/Python/Go/Rust 四语言，扫码登录后几分钟就能让 Agent 收发微信消息。

## 核心分析与要点

- **核心内容**：把微信 iLink 的 Bot 能力封装成多语言 SDK，统一提供登录、收消息、回复、群管理、多租户/多账号等接口。
- **关键亮点 / 结论**：
  - 四种语言都有包（npm / pip / go get / cargo），示例代码几乎一一对应，迁移成本低。
  - 定位是「生产级」而非玩具：支持多租户与多账号，Node.js 版本还有独有功能。
  - README 自述灵感来自 openclaw-weixin，属于 OpenClaw 生态的一环。
- **适用场景 / 启发**：给 AI Agent 加一个微信入口（客服、通知、个人助理）。注意微信侧接口的合规与封号风险，生产使用前应确认账号类型与平台政策。

## 原文 / 原始资料

原网址：<https://github.com/corespeed-io/wechatbot>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `corespeed-io/wechatbot` |
| 描述 | 微信 iLink Bot SDK for OpenClaw/AI Agent |
| Star / Fork | 705 / 94 |
| 语言 / 许可 | TypeScript / MIT |
| 最近推送 | 2026-11-02 |
| 主页 | https://wechatbot.dev |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> 5 分钟让任何 Agent 接入微信。灵感来自 [openclaw-weixin](https://github.com/Tencent/openclaw-weixin)。

> 每个 Bot 实例完全隔离（独立 HTTP 客户端、事件、消息轮询器），无全局状态、不占本地端口——一个后端进程可以同时运行多个微信账号。二维码通过回调返回，可推给 Web 前端让每个用户在自己的页面上扫码：

> 完整示例（含 PostgreSQL 自定义存储）见 [Node.js SDK 文档](https://github.com/jiweiyuan/wechatbot-landing)。

</details>
