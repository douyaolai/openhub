---
title: Claude-Cage
date: 2026-11-19
category: 开发与运维
type: 网址
source: https://github.com/Lee-xeo/Claude-Cage
tags: [隔离环境, 虚拟机, Claude, 代理]
---

# Claude-Cage

## 一句话摘要
> 为 Claude 特化的轻量虚拟机：网络与指纹隔离、多账号、远程部署、手机接续，专治封号与环境检测。

## 核心分析与要点

- **核心内容**：一个桌面程序，把虚拟机、代理、时区语言、指纹等环境因素统一在一个工作台里管理，让 Claude Desktop / Claude Code 运行在与宿主机隔离的环境中。
- **关键亮点 / 结论**：
  - 网络由 Cage 自己接管：容器内所有流量走配置好的代理，与主机隔离；时区、语言等指纹可随代理 IP 自动同步。
  - 做了全链路适配（浏览器登录、授权回调、claude code 进程），而不是只套一层 VPN。
  - 内置网络与隔离自检，关键检查失败或证据不完整时直接暂停外网——这个"宁可停也不漏"的策略是它的核心卖点。
  - 跨平台：macOS 用 macOS 虚拟机、Windows 用 Windows 虚拟机，也可选轻量 Linux 环境；支持多账号与手机接续任务。
- **适用场景 / 启发**：需要在多账号/多地区环境下稳定使用 Claude 的用户。需要清醒认识：这类工具本质是在规避服务方的环境检测，可能违反其条款，风险由使用者自负。

## 原文 / 原始资料

原网址：<https://github.com/Lee-xeo/Claude-Cage>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `Lee-xeo/Claude-Cage` |
| 描述 | Cage：为 Claude 特化的轻量化虚拟机，彻底杜绝网络泄露。多平台适配，支持多账号管理、远程部署、移动端操控。 |
| Star / Fork | 6,796 / 793 |
| 语言 / 许可 | Go / MIT |
| 最近推送 | 2026-11-19 |
| 主页 | https://lee-xeo.github.io/Claude-Cage/ |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> 作为一个只是想和 Claude 对话与合作的正常用户，受够了折腾各种 VPS，指纹浏览器，环境检测，面对封号的担惊受怕和财产损失。我们提出 **Claude Cage** 项目：**一个开箱即用的桌面程序，配置好自己的网络代理，集中管理隔离环境、时区语言和环境检查。**

> Claude Cage 让你在熟悉的系统里与 Claude 一起工作：Mac 上用 macOS 虚拟机，Windows 上用 Windows 虚拟机，也可以选择轻量的 Linux 环境。终端、浏览器、编辑器和官方 Claude Desktop 汇集在同一个工作台，项目按需共享，网络独立管理；还可以连接自己的服务器，或用手机接续电脑上的任务。支持以下几个重点功能：

> 浏览器收藏、无痕会话、Cookie、扩展、密码保险箱，以及外观、资源、存储和工具更新，见[完整使用文档](https://claude-cage.com/docs/)。

</details>
