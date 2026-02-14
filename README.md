# Gboard 🚀

**基于Go 的高性能代理计费面板。**

[![Go Version](https://img.shields.io/badge/Go-1.21+-00ADD8?style=flat&logo=go)](https://golang.org/)
[![License](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](LICENSE)
[![Release](https://img.shields.io/badge/Release-Beta-orange)]()

## 📖 简介 | Introduction

Gboard 是为了解决传统 PHP 面板在高并发和大数据量下的性能瓶颈而生的全新一代管理面板，同时我们抛弃了臃肿缓慢的 WebAPI，采用 **gRPC** 进行高性能通信，实现了节点与面板的秒级同步。

它不仅继承了 V2board/Xboard 的优秀生态，更引入了 **傻瓜化安装**、**自动环境配置** ，**快速从XB或V2B面板等转换数据的能力** 以及 **强大的落地管理**（WireGuard/Socks/HTTP 出口均衡），是大型机场和追求极致性能用户的最佳选择，也更适合小白开机场。

---

## ✨ 核心特性 | Key Features

### ⚡ 极致性能与架构
- **全 Go 语言重构**：告别 PHP，享受 Go 带来的高并发与低资源占用。
- **gRPC 高速通信**：节点秒级响应用户变动，不再依赖轮询，大幅降低延迟。
- **高定 Sing-box 后端**：完美适配，挖掘最新内核潜力。

### 🛠️ 傻瓜化部署
- **一键环境配置**：运行安装程序即可自动部署 MySQL 和 Redis，无需手动配置。
- **简单反代**：配合 Nginx/Caddy 进行反代即可上线。
- **SSH 一键装机**：面板直接连接服务器 SSH，一键部署节点。

### 🌐 强大的网络协议支持
- **全协议覆盖**：支持 SS, Vless, Vmess, Trojan, Hysteria2 等主流及新一代协议。
- **落地路由黑科技**：
    - 支持 **WireGuard 出口** / **Socks** / **HTTP** 出口。
    - 彻底解决落地机器 IP 烂的问题。
    - 单节点支持多个出口，支持 **自动切换** 与 **自动负载均衡**。

### 🛡️ 安全与备份
- **云端备份**：支持直接备份数据库到 Google Drive, Dropbox 等云存储。
- **数据可视化**：后台直观查看备份与系统状态。

---

## 🚀 快速安装 | Installation

Gboard 将复杂的部署流程简化为 4 个步骤：

### 1. 上传文件
将编译好的 `gboard` 二进制文件上传至服务器目录（例如 `/root/gboard`）。

### 2. 赋予权限
```bash
chmod +x ./gboard

3. 执行安装
Bash
./gboard


程序将自动检测环境，并在本地自动安装配置所需的 MySQL 和 Redis。按照提示设置管理员账号即可。

4. 域名反代
配置 Nginx 或 Caddy 反向代理到 Gboard 的监听端口，即可通过域名访问。

⚙️ 节点部署与管理
通信机制升级
不同于传统的 WebAPI 定时拉取，Gboard 采用 gRPC 长连接。

实时性：用户流量、限速、断开连接等操作毫秒级生效。

稳定性：在高并发场景下，数据丢失率几乎为零。

落地出口配置 (Outbound)
在节点配置中，你可以指定该节点的出口策略：

WireGuard: 填入配置即可让流量通过 WARP 或其他 WG 隧道流出。

Socks5/HTTP: 轻松复用现有的代理资源作为落地。

📝 待办事项 | Roadmap

[ ] 更多支付网关对接

[ ] 移动端适配优化

[ ] 详细的 Wiki 文档

⚠️ 免责声明 |
本项目仅供学习、技术研究和学术交流使用。请遵守您所在国家/地区的法律法规。不得用于任何非法用途。
