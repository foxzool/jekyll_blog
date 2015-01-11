---
layout: post
title: Ubuntu下基于rvm管理ruby版本
date: 2010-12-17 00:00:00
category: ruby
tags: ruby rvm ubuntu
---

不同的项目需要的ruby版本不同，需要的gems也不同，这时可以使用rvm来帮你。

首先先确保你安装了一些必须组件

```bash
    sudo apt-get install curl bison build-essential git-core zlib1g-dev libssl-dev libreadline5-dev libxml2-dev 
```
然后使用脚本安装

```bash
     $ bash < <( curl http://rvm.beginrescueend.com/releases/rvm-install-head )
```
上面的bash基本上等同于下面的脚本,两选一即可

```bash
    mkdir -p ~/.rvm/src/ && cd ~/.rvm/src && rm -rf ./rvm/ && \
    git clone --depth 1 git://github.com/wayneeseguin/rvm.git && cd rvm && ./install
```
设置.bashrc, 找到下面的一段代码

```bash
    [ -z "$PS1" ] && return 
    # Some code here... e.g.
    export HISTCONTROL=ignoreboth
```
修改为

```bash
    if [[ -n "$PS1" ]]; then
    # Some code here... e.g.
    export HISTCONTROL=ignoreboth
    fi
    [[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
```
退出终端，重新进入,测试是否安装成功

```bash
     type rvm | head -n1
```
看到下面输出说明安装成功 

```bash
     rvm is a function
```
开始安装ree，*注意这里不需要sudo*

```bash
     rvm install ree
```
安装完毕之后，让rvm默认使用ree

```bash
     rvm use ree --default
```
如果你想使用系统自带的ruby，可以这样切换

```bash
     rvm use system
```
如果你安装了多个版本的ruby，可以用rvm list 来查看