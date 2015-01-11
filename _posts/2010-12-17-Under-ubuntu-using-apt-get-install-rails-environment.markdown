---
layout: post
title: Ubuntu下用apt-get安装rails环境
category: rails
tags: ubuntu rails
---

首先使用apt-get安装ruby

```bash
    sudo apt-get install ruby
```
运行 ruby -v

```bash
    ruby 1.8.7 (2010-06-23 patchlevel 299) [i686-linux]
```
ruby安装完毕

安装rubygems，*注意,这里不要用apt-get来安装*

先从官网下载最新版rubygems,并解压

```bash
    cd /tmp;wget http://production.cf.rubygems.org/rubygems/rubygems-1.3.7.tgz

    tar zxf rubygems-1.3.7.tgz
```

运行安装程序

```bash
    sudo ruby setup.rb
```
会看到输出很多文字，最后一行是

```bash
    RubyGems installed the following executables:

    /usr/bin/gem1.8
```
然后做一个ln连接

```bash
    sudo ln -s /usr/bin/gem1.8 /usr/bin/gem
```
输入gem -v 显示 1.3.7 说明 rubygems安装完毕,开始安装rails

```bash
    sudo gem install rails
```
经过一段时间的等待和文字输出之后，运行 rails -v， 显示  Rails 3.0.3 说明安装正确

rails new newapp  开始享受rails的快乐吧！

