---
title: Firecrawl
date: 2026-11-25
category: 开发与运维
type: 网址
source: https://github.com/firecrawl/firecrawl
tags: [网页抓取, 知识库, MCP, 自托管, Agent]
---

# Firecrawl

## 一句话摘要
> 给 agent 当「知识基础设施」的抓取 API：同一套代码可本机单文件跑、可自托管全套服务、也可用云端的 550+ 数据源。

## 核心分析与要点

- **核心内容**：Firecrawl 提供三种用法，共用同一套 SDK：**Firecrawl Local**（本机单二进制，把网站转成干净 markdown，以 MCP server 形式接进 agent，并在 localhost 提供 API）、**Firecrawl Cloud**（托管服务，多了搜索与 550+ 数据提供方组成的 Alexandria 知识源）、**自托管**（从 `apps/api` 部署完整服务，带队列、worker 与数据库）。
- **关键亮点 / 结论**：
  - **三档形态覆盖了从"试一下"到"上生产"的完整路径**，而且本地版不需要数据库、队列或容器，这降低了上手门槛。
  - 除了 scrape / crawl / map，还有 **Interact**（跟页面交互）与 **Agent**（让 agent 自己决定怎么取数据）两类能力。
  - 体量极大：209k Star、10,962 Fork，TypeScript 实现，AGPL-3.0。
- **适用场景 / 启发**：需要把外部网页稳定喂给 agent 的产品；也可作为"本地优先 + 云服务"双形态架构的参考。注意 AGPL-3.0 对网络服务分发的要求，以及云端与自托管在数据合规上的差别。

## 原文 / 原始资料

原网址：<https://github.com/firecrawl/firecrawl>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `firecrawl/firecrawl` |
| 描述 | Knowledge infrastructure to make your agents smarter. Search, scrape and access 550+ data providers through one API. |
| Star / Fork | 209,598 / 10,962 |
| 语言 / 许可 | TypeScript / AGPL-3.0 |
| 最近推送 | 2026-11-25 |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> **Knowledge infrastructure to make your agents smarter. 🔥** You can use Firecrawl three ways. This repo holds the code for Firecrawl Local and the self-hosted server, along with SDKs that work with all three.

> If you don't have Rust, [Firecrawl Cloud](#firecrawl-cloud) runs the same scrape with nothing to build and no signup.

> Crawl a site and save one markdown file per page.

</details>
