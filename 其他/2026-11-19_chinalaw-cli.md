---
title: chinalaw-cli
date: 2026-11-19
category: 其他
type: 网址
source: https://github.com/nh59yytyd5-dev/chinalaw-cli
tags: [法律, CLI, MCP, Agent工具]
---

# chinalaw-cli

## 一句话摘要
> 面向 AI Agent 的中国法规检索工具：按条返回法律、行政法规与司法解释，附带效力状态、施行日期与官方来源。

## 核心分析与要点

- **核心内容**：把公开的法律、行政法规和司法解释整理成按条可查的资料库，提供 CLI、本地 MCP、托管 MCP 与自托管服务四种用法。
- **关键亮点 / 结论**：
  - 解决的是「模型引用法条不可信」的问题：模型只能提出线索，引用要回到工具取出的原文，每条都带效力状态、施行日期、版本、官方来源与核查时间。
  - 它明确声明不回答法律问题、不替代法律判断，只做可复核的检索——边界划得很清楚。
  - 用法分层合理：公开快照可离线批量用；本地 MCP 让合同与案件材料不出本机；托管 MCP 适合少量查询。
- **适用场景 / 启发**：给 Claude Code / Cursor 这类 agent 接一个可信法条源；也适合个人做合规初查。注意项目仅 9 Star，数据为公开法规整理，正式用途仍应核对官方原文。

## 原文 / 原始资料

原网址：<https://github.com/nh59yytyd5-dev/chinalaw-cli>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `nh59yytyd5-dev/chinalaw-cli` |
| 描述 | 面向 AI Agent 的中国法律法规检索 CLI |
| Star / Fork | 9 / 1 |
| 语言 / 许可 | Python / Apache-2.0 |
| 最近推送 | 2026-10-30 |
| 主页 | — |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> `chinalaw` 把公开的法律、行政法规和司法解释整理成按条可查的资料库。每一条返回的条文都带效力状态、施行日期、版本、官方来源与核查时间：模型可以提出线索，引用却要回到工具取出的原文，人和 agent 都能复核。它不回答法律问题，也不替代法律判断。

> 从[最新 release](https://github.com/nh59yytyd5-dev/chinalaw-cli/releases/latest) 下载 wheel：

> 给 Claude Code、Codex 等本机 agent 使用时，也可以从仓库安装：

</details>
