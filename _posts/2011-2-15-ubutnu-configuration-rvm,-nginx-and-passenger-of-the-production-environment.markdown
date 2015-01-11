---
layout: post
title: ubutnu配置rvm,nginx和passenger的生产环境
date: 2011-2-15 00:00:00
category: how
tags: rails rvm nginx passenger
---

下述内容参考了[A Guide to a Nginx, Passenger and RVM Server](http://blog.ninjahideout.com/posts/a-guide-to-a-nginx-passenger-and-rvm-server)

首先， 使用 root 帐号登录， 

安装git和curl

```bash
apt-get install curl git-core
```

使用脚本安装rvm

```bash
bash < <(curl -L http://bit.ly/rvm-install-system-wide)
```
脚本会自动创建一个rvm组，并将root用户加入

编辑 /root/.bashrc和/etc/skel/.bashrc

```bash
[ -z "$PS!"]  && return 
```
替换为

```bash
if [[ -n "$PS1" ]]; then
```
在文件最后加入

```bash
fi
if groups | grep -q rvm ; then
  source "/usr/local/lib/rvm"
fi
```

配置用户

```bash
#增加zool用户
adduser zool
#将zool加入rvm组
adduser zool rvm
```

登录zool用户并测试

```bash
type rvm | head -n1
```
如果显示 rvm is a function 则表示安装正确

安装ree依赖组件

```bash
aptitude install build-essential bison openssl libreadline5 libreadline-dev \
curl git-core zlib1g zlib1g-dev libssl-dev vim libsqlite3-0 libsqlite3-dev \
sqlite3 libreadline-dev libxml2-dev git-core subversion autoconf
```

安装ree

```bash
rvm install ree
```

设为默认环境

```bash
rvm use ree --default
```

安装passenger和nginx

```bash
gem install passenger
rvmsudo passenger-install-nginx-module
```

配置nginx里的ruby环境

```bash
    passenger_root /usr/local/rvm/gems/ree-1.8.7-2010.02/gems/passenger-3.0.0;
    passenger_ruby /usr/local/rvm/wrappers/ree-1.8.7-2010.02/ruby;
```

设置nginx开机脚本

```bash
curl -L http://bit.ly/nginx-ubuntu-init-file > /etc/init.d/nginx
chmod +x /etc/init.d/nginx
update-rc.d nginx defaults
/etc/init.d/nginx start
```

原文中后面的step6,7关于Capistrano的环境配置以后再另文详述