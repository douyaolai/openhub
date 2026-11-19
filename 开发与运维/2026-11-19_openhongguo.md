---
title: openhongguo
date: 2026-11-19
category: 开发与运维
type: 网址
source: https://github.com/beilunyang/openhongguo
tags: [SDK, 短剧, 多语言, 逆向]
---

# openhongguo

## 一句话摘要
> 红果短剧的非官方匿名 SDK：Go/Node/Android/iOS/RN/Flutter 多语言，免登录即可查目录、详情、弹幕与播放地址。

## 核心分析与要点

- **核心内容**：以匿名设备身份请求红果短剧接口，支持浏览/搜索短剧、读取短剧与分集详情、弹幕，并取得分集播放地址与内容密钥；同时提供 `ohg` 命令行工具。
- **关键亮点 / 结论**：
  - Go 写核心、其他语言由 Go 编译成绑定，因此各语言行为严格一致——这是多语言 SDK 里比较省心的做法。
  - 客户端选项完整：分页、错误处理、重试与超时、加密分集、匿名设备、自动更换设备、自定义 HTTP。
- **适用场景 / 启发**：作为「多语言 SDK 工程化」的参考（一套实现 + 多语言绑定 + CLI），或做短剧数据的学习性研究。注意仓库为非官方实现，README 写明仅供学习、禁止商用、不得用于大规模采集，接口随时可能失效。

## 原文 / 原始资料

原网址：<https://github.com/beilunyang/openhongguo>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历文件树、源码、Issue 与 Commit。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `beilunyang/openhongguo` |
| 描述 | 红果短剧的非官方匿名 SDK，提供 Go、Node.js、Android、iOS、React Native 和 Flutter 版本，附命令行演示程序 ohg CLI |
| Star / Fork | 537 / 172 |
| 语言 / 许可 | Go / Apache-2.0 |
| 最近推送 | 2026-11-18 |
| 主页 | — |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> openhongguo 是红果短剧（Hongguo）的非官方 SDK，提供 Go、Node.js、Android、iOS、React Native 和 Flutter 版本。SDK 可以浏览短剧目录、搜索短剧、读取短剧和分集的详情与弹幕，并取得分集的播放地址和内容密钥。

> SDK 用匿名设备发送所有请求，不需要登录。Go 以外的 SDK 都由 Go SDK 编译而成，所以各语言的行为相同。

> 第一次请求时，SDK 注册一台匿名设备，并把设备档案保存到 `anonymous.json`。以后的请求都使用这台匿名设备。

</details>
