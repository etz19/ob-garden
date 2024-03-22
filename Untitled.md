---
title: The Art of Perfumery and the Power of Aroma
tags: [perfumery, aroma, scent collection, material synergy, olfactory exploration]
---
```markdown
# Docker 部署指南

Docker 提供了一种高效、一致的方法来部署应用程序。在 Linux 环境下，强烈推荐使用 Docker 进行部署。以下是使用 Docker 部署的简要指南。

## 创建 docker-compose.yml 文件

首先，在你选择的目录下创建一个名为 `docker-compose.yml` 的文件，文件内容如下：

```yaml
version: '3'

services:
  cogpt-api:
    image: geniucker/cogpt:latest
    environment:
      - HOST=0.0.0.0
    ports:
      - 8080:8080
    volumes:
      - ./db:/app/db
      - ./log:/app/log
    restart: unless-stopped
    container_name: cogpt-api
```

## 使用开发版镜像

如果你希望使用开发版而不是最新稳定版，可以将 `image` 字段的值从 `geniucker/cogpt:latest` 更改为 `geniucker/cogpt:dev`。

## 修改监听端口

默认情况下，服务会监听在端口 `8080` 上。如果需要更改监听端口，可以编辑 `docker-compose.yml` 文件中的 `ports` 部分。例如，将 `8080:8080` 修改为 `8081:8080`，即可使服务监听在 `8081` 端口。

## 调整配置

- **环境变量**：可以在 `docker-compose.yml` 文件的 `environment` 部分修改环境变量。
- **数据库和日志路径**：`db` 和 `log` 的路径可以在 `volumes` 部分进行修改。
- **使用 .env 文件**：为方便配置管理，可以将 `.env.example` 文件复制为 `.env` 并根据需要进行修改。

## 启动服务

完成上述配置后，在含有 `docker-compose.yml` 文件的目录下运行以下命令启动服务：

```bash
docker compose up -d
```

此命令将在后台启动服务。所有的配置选项均在官方文档的“配置”部分列出，可根据需要进行查阅和修改。

通过以上步骤，你将能够在 Linux 系统上通过 Docker 高效部署你的应用。
```