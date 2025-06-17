---
title: "WebDAV"
weight: 7
menu:
  main:
    parent: "advanced"
    name: "WebDAV"
    weight: 7
---


## 功能概述

本项目通过WebDAV协议将网盘文件映射为本地STRM虚拟文件系统，专为媒体播放器优化设计。

> **版本说明**：青春版（播放专用）
> - ✅ 支持STRM文件解析播放
> - ✅ 智能ISO虚拟化处理
> - ✅ 基础目录浏览
> - ❌ 文件写入/删除操作

## 连接配置

### 基础信息
```ini
服务器地址: https://你的域名或IP地址:8091/dav/
认证方式: Basic Auth
账号密码: 与转存系统登录凭证相同

```

推荐客户端
1. Infuse
2. Vidhub

⚠️ 警告：不建议使用MacOS自带的WebDAV挂载功能

详细连接步骤
Infuse 配置示例
打开「添加文件源」→ 选择「WebDAV」

填写参数：

```yaml

名称: 自定义显示名称
地址: your_domain.com 或 x.x.x.x
路径: /dav/
端口: 8091
用户名/密码: 转存系统账号

```