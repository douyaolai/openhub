---
title: TrendRadar
date: 2026-11-19
category: 产品与商业
type: 网址
source: https://github.com/joyce677/TrendRadar
tags: [热点监控, 舆情, 推送, 内容运营]
---

# TrendRadar

## 一句话摘要
> 一键盯住 35 个平台热榜，按关键词筛完自动推到企微/飞书/钉钉/Telegram，号称 30 秒网页部署。

## 核心分析与要点

- **核心内容**：定时抓取今日头条、百度热搜、微博、抖音、知乎、B 站等 35 个平台的热榜，做关键词过滤与排序，再通过多渠道推送；同时开放 `/api/trends.json` 与图片版接口，方便别的程序调用。
- **关键亮点 / 结论**：
  - 卖点是「部署成本」而不是技术深度：一条 Cloudflare Pages / GitHub Pages 就能跑起来，不需要服务器。
  - 数据源并非自己爬，README 明确说明使用了 newsnow 项目提供的 API。
  - 支持「智能推送策略」，即只在命中关键词时通知，解决"热榜噪音大"的问题。
- **适用场景 / 启发**：自媒体选题、品牌舆情初筛、个人资讯降噪。适合不想写代码但要盯热点的人；若要做严肃舆情分析，单靠热榜排序不够。

## 原文 / 原始资料

原网址：<https://github.com/joyce677/TrendRadar>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `joyce677/TrendRadar` |
| 描述 | 一键监控今日头条、百度热搜、微博、抖音、知乎、B站等35个平台，智能关键词筛选，自动生成热点分析报告。支持企业微信、飞书、钉钉、Telegram推送，30秒网页部署，1分钟手机通知，无需编程基础。还有文字和图片版api可调用 |
| Star / Fork | 1,908 / 1,133 |
| 语言 / 许可 | HTML / GPL-3.0 |
| 最近推送 | 2026-10-20 |
| 主页 | https://news.fengpt.eu.org |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> 支持**企业微信**、**飞书**、**钉钉**、**Telegram**，消息直达手机

> **💡 提示：** 想要**实时更新**的网页版？fork 后，进入你的仓库 Settings → Pages，启用 GitHub Pages。[效果预览](https://sansan0.github.io/TrendRadar/)。

> 在你 Fork 后的仓库中，进入 `Settings` > `Secrets and variables` > `Actions` > `New repository secret`，然后根据需要配置以下任一或多个通知平台：

</details>
