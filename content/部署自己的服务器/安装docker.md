---
tags: [docker, installation, linux, tutorial]
date: [2024-03-03]
---

# 在 Linux 服务器上安装 Docker 的教程

Docker 是一个开源的应用容器引擎，允许开发者打包他们的应用以及依赖包到一个可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。安装 Docker 可以让你的开发和部署过程更加高效、简化。

## 前提条件

- 一台运行 Linux 的服务器
- 对服务器有 sudo 权限或 root 访问权限

## 安装步骤

### 步骤 1: 更新软件包列表

打开终端，并执行以下命令以更新你的服务器的软件包列表：

```bash
sudo apt-get update
```

### 步骤 2: 安装所需的软件包

安装 `apt-transport-https`, `ca-certificates`, `curl`, `software-properties-common` 这些软件包，这些是 Docker 安装过程中所需的：


```bash
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

### 步骤 3: 添加 Docker 的官方 GPG 密钥

执行以下命令，添加 Docker 官方的 GPG 密钥：

bashCopy code

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### 步骤 4: 设置 Docker 稳定版仓库

添加 Docker 的稳定版仓库到你的系统中：

bashCopy code

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`

### 步骤 5: 再次更新软件包列表

再次更新你的服务器的软件包列表，确保能够从 Docker 仓库中下载：

bashCopy code

`sudo apt-get update`

### 步骤 6: 安装 Docker CE

现在你可以安装 Docker 社区版（CE）了：

bashCopy code

`sudo apt-get install docker-ce`

### 步骤 7: 验证安装

安装完成后，你可以运行以下命令来验证 Docker 是否正确安装：

bashCopy code

`sudo docker run hello-world`

如果安装成功，你将会看到一条消息，说明你的 Docker 正在运行。

## 总结

至此，你已经在你的 Linux 服务器上成功安装了 Docker。你现在可以开始使用 Docker 来容器化你的应用了。

