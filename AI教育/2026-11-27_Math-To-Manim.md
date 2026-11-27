---
title: Math-To-Manim
date: 2026-11-27
category: AI教育
type: 网址
source: https://github.com/HarleyCoops/Math-To-Manim
tags: [数学动画, Manim, 物理解释, Lean 形式化, 研究笔记]
---

# Math-To-Manim

## 一句话摘要
> 把文本与图片变成数学/物理动画与学习笔记，且每部片子都配论文、Manim 源码与 Lean 形式化证明。

## 核心分析与要点

- **核心内容**：一个面向数学与物理的动画生成项目，输入是文本或图片，输出是"史诗感"的解释动画 + 学习笔记。它的特色不在于画面，而在于**每部片子背后有可核对的推导**：以 Featured 作品《The Mix That Cannot Kill a Pole》为例，同时提供论文 PDF、Lean 形式化文件、Manim 源码与逐阶段产出记录。
- **关键亮点 / 结论**：
  - **把动画当作"论证的可视化"而非装饰**：片子里出现的结论在论文与 Lean 文件里都有对应定理（如极点是否在混合后仍存在）。
  - 另含 Neon-first 的命令行工具（`src/neon/`）与"从笔记本草图到 Base 12 计算机"这类完整案例，说明它能覆盖从概念到实现的长链条。
  - 有 Architecture & Testing 章节，工程面不是玩票。
- **适用场景 / 启发**：做数学/物理科普视频、课件的团队；也适合研究"如何让生成内容可验证"——它给出的答案是：动画旁边放形式化证明。2,966 Star，MIT，Python。

## 原文 / 原始资料

原网址：<https://github.com/HarleyCoops/Math-To-Manim>

> 抓取说明：按仓库类链接规则，仅取 README 与仓库元数据，未遍历源码与 Issue。

<details>
<summary>展开查看：仓库速览</summary>

| 项 | 值 |
|---|---|
| 仓库 | `HarleyCoops/Math-To-Manim` |
| 描述 | Create Epic Math and Physics Animations & Study Notes From Text and Images. |
| Star / Fork | 2,966 / 329 |
| 语言 / 许可 | Python / MIT |
| 最近推送 | 2026-11-24 |

</details>

<details>
<summary>展开查看：README 摘录（逐字照录）</summary>

> Math-To-Manim turns frontier mathematics into verified 3D Manim and Blender films in a single CLI call. The film above is the newest one. These are 20 of the films that came before it.

> The mix, with delays that are zero before they start:

> $$D(u) = -g(u) + 3\,g(u-\log 2) - 2\,g(u-\log 4)$$

</details>
