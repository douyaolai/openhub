---
title: dsh-desktop
date: 2026-11-19
category: 开发与运维
type: 网址
source: https://github.com/anywhere-labs/dsh-desktop
tags: [DSH, 桌面客户端, 插件生态, Electron]
---

# dsh-desktop

## 一句话摘要
> 把 DeepSeek Harness 的 Web UI、Host 服务与插件系统包成原生桌面应用——桌面本身也是一个插件，36k Star。

## 核心分析与要点

- **核心内容**：为 DeepSeek Harness 做的桌面壳，集成其本地 Web UI、Host 服务与插件机制，额外提供窗口、托盘、终端、自动更新与工作配置。项目固定并原样运行特定上游版本，能力扩展全部走 DSH 的插件接口。
- **关键亮点 / 结论**：
  - 「万物皆插件」贯穿到桌面本身：桌面端不是一个特例分支，而是插件生态里的一个成员，这降低了与上游分叉的成本。
  - 三平台安装包齐全：Windows x64（NSIS）、macOS Universal（DMG）、Linux x64/arm64（deb / AppImage / tar.gz）。
  - README 明确声明这是独立社区项目，与深度求索无隶属、合作或授权关系，并解释了 Contributors 里出现上游贡献者的原因（fork 继承）。
- **适用场景 / 启发**：想在桌面端用 DSH 而不折腾环境的人；也是「给 Web 应用套原生壳 + 复用上游插件系统」的工程参考。

## 原文 / 原始资料

原网址：<https://github.com/anywhere-labs/dsh-desktop>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `anywhere-labs/dsh-desktop` |
| 描述 | 为 DeepSeek Harness (DSH) 插件生态打造的现代化桌面端解决方案。万物皆「插件」，桌面本身也是「插件」。 |
| Star / Fork | 36,409 / 1,654 |
| 语言 / 许可 | TypeScript / MIT |
| 最近推送 | 2026-11-19 |
| 主页 | https://dshdesktop.cn |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> DSH Desktop 将 [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) 的本地 Web UI、Host 服务和插件系统集成到原生桌面应用中。项目固定并原样运行特定上游版本；DSH Desktop 提供窗口、托盘、终端、更新和工作配置，并通过 DeepSeek Harness 提供的插件机制与上游能力组合。

> 当前正式安装包支持 Windows x64、macOS Universal 和 Linux（x64 与 arm64）。无需额外环境，下载安装，一键使用。

> Linux 安装包只在 GitHub Release 发布，x64 与 arm64 各有三种格式：

</details>
