---
title: "安装与部署"
weight: 2  # 控制章节顺序
---

> #### 为了更便捷地部署 `cloud189-auto-save-pro` 项目，推荐使用 `docker-compose` 进行部署。以下是详细的部署步骤和相关配置说明。


### 使用 `docker-compose` 部署

```yaml
version: "3"

services:
  cloud189:
    image: xia1307/cloud189-auto-save-pro:latest
    container_name: cloud189pro
    restart: unless-stopped
    privileged: true
    ports:
      - "3000:3000" 
      - "8091:8091"
    volumes:
      - /cloud189pro/data:/home/data
      - /cloud189pro/strm:/home/strm
    environment:
      - PUID=0
      - PGID=0
      - NODE_OPTIONS=--dns-result-order=ipv4first
      - SERVICE_CODE=购买的激活码

```
### Docker 命令部署
```bash
docker run -d \
  --name cloud189pro \
  --restart unless-stopped \
  --privileged \
  -p 3000:3000 \
  -p 8091:8091 \
  -v /cloud189pro/data:/home/data \
  -v /cloud189pro/strm:/home/strm \
  -e PUID=0 \
  -e PGID=0 \
  -e NODE_OPTIONS=--dns-result-order=ipv4first \
  -e SERVICE_CODE=购买的激活码 \
  xia1307/cloud189-auto-save-pro:latest
```


### 配置说明

#### 端口映射
- **`ports`**：将容器内部的端口映射到宿主机上。
  - `3000:3000`：将容器的 3000 端口映射到宿主机的 3001 端口，仅允许本地访问。3000 端口是转存系统端口，在项目运行时，转存系统通过该端口提供服务。你可以更改前面的3000为其他端口，但是请注意，端口号必须是未被占用的端口。
  - `8091:8091`：同理，将容器的 8091 端口映射到宿主机的 8091 端口。8091 端口为反代服务端口，在项目运行时，反代服务通过该端口提供服务。你可以更改前面的8091为其他端口，但是请注意，端口号必须是未被占用的端口。

#### 数据挂载
- **`volumes`**：将宿主机的目录挂载到容器内部。
  - `/cloud189pro/data:/home/data`：将宿主机的 `/cloud189pro/data` 目录挂载到容器的 `/home/data` 目录。
  - `/cloud189pro/strm:/home/strm`：将宿主机的 `/cloud189pro/strm` 目录挂载到容器的 `/home/strm` 目录。

#### 环境变量
- **`environment`**：设置容器的环境变量。
  - `PUID` 和 `PGID`：分别表示用户 ID 和组 ID。
  - `NODE_OPTIONS=--dns-result-order=ipv4first`：用于避免双栈地址导致的问题。
  - `SERVICE_CODE`：需要替换为你购买的激活码。
