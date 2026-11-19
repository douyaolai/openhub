---
title: Headscale自建组网
date: 2026-11-19
category: 开发与运维
type: 网址
source: https://www.dhao2001.com/2025/01/11/headscale-self-hosted-quick-start/
tags: [Headscale, Tailscale, WireGuard, 异地组网, 内网穿透, Nginx]
---

# Headscale自建组网

## 一句话摘要
> 一篇完整的实操记录：用 Docker + Nginx 自建 Headscale 中央服务器，把 Tailscale 的控制面换到自己手里，顺带解决 MagicDNS、子网路由与自签名证书三件麻烦事。

## 核心分析与要点

- **核心内容**：作者原本用 ZeroTier 做异地组网，后来转向 Tailscale 生态，最终选择开源的 Headscale 自建控制服务器。文章从术语讲起（Tailscale、控制服务器、DERP 中继、Headscale），再给出完整步骤：准备公网服务器与域名 → 改 `config-example.yaml` → 起 Docker 容器 → 开防火墙 → Nginx 反代 → 加用户 → 注册设备 → MagicDNS → 子网路由 → 自签名 HTTPS 证书。

- **关键亮点 / 结论**：
  - **把"为什么自建"讲清楚了**：Tailscale 官方允许自建 DERP 中继，但中央控制服务器是闭源、不允许自行部署的；Headscale 正是它的开源实现（BSD 协议），所以能真正把组网信息握在自己手里。
  - **安全边界有交代**：设备间流量端到端加密、私钥只在设备本地，因此中继服务器通常无法解密流量——这解释了"为什么用别人的中继也不等于泄露内容"。
  - **踩坑点写得很具体**：MagicDNS 与多级域名的配置、DNS 记录 JSON 文件格式的坑、子网路由（Subnet Router）要同时在客户端设置转发并在服务器端授权，这几处正是自建时最容易卡住的地方。
  - **附赠的自签名证书部分很实用**：签发 Root CA → 签发子证书 → Nginx 绑定 → 把根证书分别装进 Windows 与 Linux，形成一套可复用的内网 HTTPS 方案。
  - **提到了 Headscale-UI**：给不习惯敲命令的人一个 Web 管理界面，需要为它配 API Key。

- **适用场景 / 启发**：
  - 适合有公网 VPS、想把异地组网控制权收回本地的运维/自建玩家；也适合当作 Headscale 的部署清单照着做。
  - 文章写于 2025-01，Headscale 迭代较快，**具体配置项名称与命令建议对照当前版本文档**；文中示例代码块在抓取时被行号渲染打断，无法原样复现，需要看原文。
  - 前提是"有一台可达的公网服务器 + 域名"，纯家用无公网 IP 的场景需要另想办法。

## 原文 / 原始资料

原网址：<https://www.dhao2001.com/2025/01/11/headscale-self-hosted-quick-start/>

> 抓取说明：页面为静态博客，正文可抓取；但文中的配置示例与命令块被页面的代码高亮渲染成逐行行号，无法可靠还原，因此这里只摘录叙述性段落，代码请回原文查看。

<details>
<summary>展开查看：文章结构</summary>

| 段落 | 内容 |
|---|---|
| 术语 | Tailscale、Tailscale 服务器（Control Server / DERP Server）、Headscale |
| 技术细节 | Docker 运行 Headscale、Nginx 反代、Web UI、子域名入口、与现有站点共存 |
| 配置服务器 | 准备工作、配置文件、准备 Docker、启动容器、开放防火墙、Nginx 反代 |
| 开始组网 | 添加用户（Users vs Namespaces）、常规注册、预认证密钥、MagicDNS、DNS JSON 格式问题 |
| 子网路由 | 原理、转发客户端设置、服务器授权、Linux 客户端设置 |
| 附赠 | 自签名 HTTPS 证书：Root CA、子证书、Nginx 绑定、根证书装入 Windows / Linux |

</details>

<details>
<summary>展开查看：关键原文摘录（逐字照录）</summary>

**动机**

> 后来听说了Tailscale这个工具，再后来了解到了还有Headscale这样的开源实现，觉得这玩意似乎更加优雅，于是，折腾了半个晚上后总算把网络组起来了。在这里记录一下详细的过程。

**Tailscale 是什么**

> Tailscale是一个基于WireGuard协议的组网工具。这一协议的好处是，在建立设备间通信时会尝试打洞，从而实现设备之间的P2P点对点通信，即便这些设备位于一些NAT网关后（不过根据NAT类型不同，打洞成功的可能性也不同，可参见：How NAT traversal works）。

**两个服务器角色的区分**

> 值得注意的是，在Tailscale中，中央服务器和中继服务器可以是不同的服务器。

**为什么需要 Headscale**

> Tailscale官方尽管允许自行部署DERP服务器，但Tailscale中央服务器程序是闭源的，官方也不允许我们部署。而人们又常常因为一些原因，想要或者需要搭建自己控制的中央服务器，真正地将所有信息都掌控在可控范围内。

**中继能不能看到流量**

> 值得注意的是，所有设备间流量在网络上传输时都是加密的，且私钥都在设备本地，因此通常认为中继服务器是无法解密传输流量的。

**本文的技术选型**

> 这篇文章采用的小技术细节：Headscale运行在Docker上，方便管理；

**前置条件**

> 一台具备公网IP的服务器（至少对你来说，这个IP地址应当确保在你的应用场景下，总是可达的）

</details>
