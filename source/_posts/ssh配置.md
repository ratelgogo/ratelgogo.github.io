---
title: ssh配置
date: 2016-12-13 15:24:18
tags: mac
categories: config
---

# ssh 配置

利用ssh远程连接服务器命令：
```shell
ssh user@hostname -p port

```

每次输入hostname，又麻烦又难记，所以可以在～/.ssh/config中配置host

```shell
	Host 别名
		HostName 主机ip
		Prot 端口（默认则无需配置）
		User 登陆用户名
		IdentityFile 登陆密钥文件（免密码登录时需要）
```

下次登录是只要输入`ssh 别名` +密码就能登录
