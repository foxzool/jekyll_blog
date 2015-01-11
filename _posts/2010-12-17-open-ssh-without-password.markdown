---
layout: post
title: 开启ssh无密码登录
date: 2010-12-17 00:00:00
category: how
tags: ubuntu
---

首先生成公钥

```bash
    ssh-keygen -t rsa
```

一路回车，会在~/.ssh目录下生成公钥和私钥.

将公钥复制到需要登录的服务器

```bash
    ssh-copy-id user@host
```

OK，完成了设置。

P.S. 如果服务器没有开启公钥登录，请编辑 /etc/ssh/sshd_config, 确保

```bash
    PubkeyAuthentication yes
```

并重启ssh服务

```bash
    sudo /etc/init.d/ssh restart
```

