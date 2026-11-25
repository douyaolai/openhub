---
title: OpenTrading
date: 2026-11-25
category: Web3与金融
type: 网址
source: https://github.com/CheshireMew/OpenTrading
tags: [行情看盘, 策略回测, Pine脚本, 加密货币, 自托管]
---

# OpenTrading

## 一句话摘要
> 自托管的开源看盘与策略模拟工具：多图行情、Pine 编辑器与回测、DCA 模拟、美元流动性看板，主打加密货币。

## 核心分析与要点

- **核心内容**：一个本机运行的行情与投研工作台，分五块：**看盘**（单/双/四图、自选列表、绘图、技术指标、Pine 编辑器与策略测试器）、**市场观察**（市场信号、Binance 合约市场、Web3 排行，以及交易所支持的股票品种）、**投资工具**（币种对比、DCA 定投模拟、比特币减半周期观察）、**历史模拟**（Pine 策略回测、收益曲线与交易记录）、**美元流动性**（看板 + 命令行查跨资产日线与宏观历史）。
- **关键亮点 / 结论**：
  - **Pine 脚本能在本地跑历史模拟**，是它和普通行情站最大的区别：不用把策略交给第三方平台。
  - 数据以加密货币为主，但整合了 Binance 合约与部分股票品种，适合跨市场对照。
  - 部署门槛明确：Windows 验收、Python 3.12.x、Node ≥ 22.12；数据库可选 SQLite 起步。
- **适用场景 / 启发**：想自己掌控策略回测环境、又不愿付费买平台的人。注意 AGPL-3.0（衍生服务需开源）、仅 23 Star 且仓库很新，回测结果不等于实盘表现。

## 原文 / 原始资料

原网址：<https://github.com/CheshireMew/OpenTrading>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `CheshireMew/OpenTrading` |
| 描述 | 未填写 |
| Star / Fork | 23 / 5 |
| 语言 / 许可 | Python / AGPL-3.0 |
| 最近推送 | 2026-11-25 |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> 打开首页即可选择交易对与周期、添加指标或 Pine 脚本，也可以比较资产、进行定投模拟和回看策略结果。行情以加密货币为主。

> 当前验收平台为 **Windows**。需要 Git、Python **3.12.x**、Node.js **≥ 22.12.0** 和 npm。在准备存放项目的目录打开 PowerShell：

> 缓存直接使用有容量上限的进程内存，模型 API Key 为可选项。PostgreSQL、手动启动、日志位置及排障见[启动指南](docs/GETTING_STARTED.md)。

</details>
