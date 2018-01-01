---
title: centos安装docker
date: 2017-11-21 16:04:30
tags: 
	- centos
	- docker
---

### 系统要求

安装Docker CE 需要版本7以上的64位centos，而且必须启用centos-extras源。

### 卸载旧版本

```bash
sudo yum remove docker docker-common docker-selinux docker-engine
```

### 安装DockerCE

#### 通过YUM安装

##### 配置官方源

1. 安装依赖包

   ```Bash
   sudo yum install -y yum-utils \
   device-mapper-persistent-data \
   lvm2
   ```

   ​

2. 配置稳定版本的源

   ```bash
   sudo yum-config-manager \
       --add-repo \
       http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo(官方源https://download.docker.com/linux/centos/docker-ce.repo比较慢）
   ```

##### 安装

```bash
sudo yum -y install docker-ce
```



### 启动docker

```Bash
sudo systemctl start docker
```

#### 建立docker用户组

> 默认情况下，`docker` 命令会使用 [Unix socket](https://en.wikipedia.org/wiki/Unix_domain_socket) 与 Docker 引擎通讯。而只有 `root` 用户和 `docker` 组的用户才可以访问 Docker 引擎的 Unix socket。出于安全考虑，一般 Linux 系统上不会直接使用 `root` 用户。因此，更好地做法是将需要使用 `docker` 的用户加入 `docker` 用户组。

```Bash
sudo groupadd docker
sudo usermod -aG docker $USER
```



### 卸载docker

1. ```bash
   sudo yum remove docker-ce
   ```

2. 删除docker相关的文件

   ```Bash
   sudo rm -rf /var/lib/docker
   ```

   ​