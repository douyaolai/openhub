---
title: ClaudeCode固定节点
date: 2026-11-19
category: AI与技术
type: 文字
source: 手动输入
tags: [Claude Code, 代理配置, sing-box, macOS, LaunchAgents, 防漏IP]
---

# ClaudeCode固定节点

## 一句话摘要
> 一段可直接交给本机 Agent 执行的 Prompt：在 macOS 上为 Claude Code 单独建一条固定出口的代理通道（sing-box/xray + LaunchAgents 常驻），再把代理与时区写进 settings.json 和 zsh 启动环境，堵住"首包漏 IP"和"进程逃逸代理"两个口子。

## 核心分析与要点

- **核心内容**：这不是一篇给人阅读的文章，而是一份**执行型 Prompt**——通篇以"检查 → 执行 → 验证"的指令形式写成，目标是让本机 Agent 自动完成五件事：① 排查 `.claude/settings.json`、`.zshrc`、系统代理、utun 网卡与常驻 claude 进程的漏 IP 风险；② 用 sing-box 或 xray 建一条与日常代理解耦的常驻通道（回环 17890 HTTP / 17891 SOCKS5，权限 700/600，LaunchAgents 保活）；③ 走该通道实测出口 IP 与时区、并测 Anthropic API 握手延迟；④ 用 settings.json 的 `env` 与 `.zshrc` 的包装函数双层注入代理与时区；⑤ 校验 JSON / zsh 语法、确认服务 running，并给出清理与 `lsof` 自检命令。

- **关键亮点 / 结论**：
  - **"双层绑定"是这段 Prompt 最有价值的设计**：只改 `settings.json` 会漏掉进程启动瞬间读不到配置的那几秒，只改 shell 环境又会漏掉由 IDE／图形界面拉起的进程；两者都注入才能覆盖"启动首包盲区"。
  - **明确禁止盲猜端口**：写了"不要盲猜 7897"，要求先扫描本机实际监听的 HTTP 端口并**向用户确认后再绑定**——这一条避免了最常见的失败方式（绑定了一个没在跑的端口）。
  - **`NO_PROXY` 是防误伤的护栏**：把 `localhost,127.0.0.1,::1` 放进 `NO_PROXY`，否则本地 MCP 服务、本地开发端口会被一起代理出去，直接报错。
  - **有回滚与自检意识**：要求无损合并（保留 `model`、`mcpServers`、`hooks`）、不改 macOS 全局时钟与语言、不强杀当前终端，最后给一行清理旧进程 + 重载环境的命令，以及用 `lsof` 确认"没有外部直连"的检查方法。
  - **权限与保活写得具体**：目录 700、文件 600，LaunchAgents 开 `RunAtLoad` 与 `KeepAlive`，并发上限与订阅凭证的落盘风险被隐含地照顾到了。

- **适用场景 / 启发**：
  - 适合 macOS 上长期使用 Claude Code、且需要出口国家稳定的开发者；照做能把"今天能连、明天跳区"的随机故障收敛成可检查的固定链路。
  - 也适合当作**执行型 Prompt 的写作样本**：每一步都有可验证的产出（端口、IP、时区、延迟、服务状态、lsof 结果），而不是"帮我配置一下"这种无法验收的指令。
  - 使用前需自行判断三点：其一，依赖 macOS + Homebrew，Windows/Linux 需改写（`launchd` 换成 systemd/计划任务）；其二，把订阅节点写进本机常驻服务意味着凭证长期落盘，权限设置必须真正生效；其三，用代理与指纹隔离规避平台环境检测，可能违反服务方条款，风险由使用者自负——这一点与本站已归档的《Claude 防封号与虚拟卡订阅指南》是同一类问题。

## 原文 / 原始资料

以下为用户提供的原始 Prompt，完整保留、未做任何改写或删减：

---

【复制下方 Prompt 发给你的本机 Agent】

请帮我为本机的 Claude Code 部署一套「本机固定节点与防漏 IP」方案，严格按以下步骤自动检查并执行（不要覆盖我原有的其他配置）：

1. 本机隐患检查：
- 检查家目录下的 .claude/settings.json、.zshrc、系统代理与 utun 网卡状态，以及后台是否有常驻的 claude 守护进程，列出当前的漏 IP 或跳区风险点。

2. 建立独立的本机常驻代理通道（与日常代理软件解耦）：
- 如果我提供了固定地区的节点链接（vless / ss / vmess 等常见协议）：请通过 Homebrew 安装 sing-box 或 xray，将配置写入家目录下的 .claude-proxy 文件夹（目录与文件权限设为 700 和 600），监听本机回环地址的 17890 端口（HTTP）与 17891 端口（SOCKS5），并创建 macOS 用户级 LaunchAgents 开机自启守护服务（开启 RunAtLoad 与 KeepAlive），确保即使关掉日常代理或切换全局节点，17890 端口依然固定走该节点出站。
- 如果我没有提供独立节点链接：请先扫描我本机当前代理软件实际监听的本地 HTTP 端口（不要盲猜 7897），向我确认后再绑定。

3. 实测出口 IP 与提取对应时区：
- 用命令行走本机 17890 代理端口请求 ipinfo 的 json 接口验证连通性，提取该出口 IP 真实的国家、城市与 timezone 时区字段（例如 America/Los_Angeles 或 Asia/Singapore），并测试连接 Anthropic 官方 API 接口的握手延迟。

4. 配置文件与启动环境双层绑定（堵住启动首包盲区 + 放行本地服务）：
- 无损合并修改 .claude/settings.json（保留原有的 model、mcpServers、hooks 等所有字段），在 env 字段中将 HTTP_PROXY 与 HTTPS_PROXY 指向本机 127.0.0.1 的 17890 端口（带完整 http 协议头），并将 NO_PROXY 设为 localhost,127.0.0.1,::1（防止本地 MCP 与本地开发端口被误代理报错）。
- 在 .zshrc 中为 claude 命令添加或更新同名包装函数，在进程启动前同步注入上述三个代理环境变量，以及第 3 步实测出的出口对应时区 TZ 变量与 LANG="en_US.UTF-8"（不改动 macOS 系统全局时钟与语言，消除启动时加载配置文件前的首包盲区）。如有副号配置目录（如 .claude-pro2）也请一并同步。

5. 语法校验与连接自检：
- 校验 settings.json 的 JSON 格式与 .zshrc 的语法无误，确认自启服务状态为 running。
- 不要强杀我当前正在使用的终端会话；最后给我一行清理旧后台进程并重载环境的命令，以及用 lsof 检查 claude 所有网络连接是否均指向本机 17890 端口（无外部直连）的自检命令。

我的固定节点信息如下（若留空请先扫描我本机现有代理端口）：
[在这里粘贴你的节点链接，或留空]
