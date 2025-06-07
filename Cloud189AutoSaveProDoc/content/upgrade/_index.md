---
title: "升级指引"
weight: 2  # 控制章节顺序
---

### Docker Compose 方式升级镜像
```bash
docker-compose pull xia1307/cloud189-auto-save-pro:latest
docker-compose down
docker-compose up -d
```

### Docker 方式升级镜像
```bash
docker stop cloud189pro
docker rm cloud189pro
docker pull xia1307/cloud189-auto-save-pro:latest

根据安装命令中启动即可
```