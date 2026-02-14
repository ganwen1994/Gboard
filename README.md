Gboard

基于 V2board 与 Xboard 二次开发的高性能 Go 面板，采用全新架构设计，支持多协议扩展与高并发场景，专注于大规模部署与稳定运行。

高性能 · 易部署 · 可扩展 · 面向大规模用户优化

🚀 项目特点

Go 重构核心架构

支持 SS / VLESS / VMess / Trojan / Hysteria2

支持多出口与自动负载均衡

面向高并发与大数据场景优化

相比传统 PHP 面板性能与实时同步能力显著提升

⚡ 一键部署

上传 gboard 至服务器 → 赋予执行权限：

chmod +x gboard
./gboard


程序自动完成 MySQL、Redis 安装与初始化，配置域名反代即可上线。

🗂 数据备份

支持本地备份查看与下载，并可云备份至 Google Drive、Dropbox 等平台。

🔧 后端架构

深度适配 sing-box

面板可通过 SSH 直连服务器安装节点

支持 WireGuard / Socks / HTTP 出口

单节点支持多个出口，自动切换与负载均衡

采用 gRPC 通信，节点秒级同步用户变动
