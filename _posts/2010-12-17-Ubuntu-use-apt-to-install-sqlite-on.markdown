---
layout: post
title: Ubuntu上用apt安装sqlite
date: 2010-12-17 00:00:00
category: how
tags: ubuntu sqlite
---

很简单

```bash
    sudo apt-get install sqlite3 libsqlite3-dev
```
检查版本

```bash
    ~ > sqlite3 -version
    3.7.2
```

通过命令行进入数据库

```bash
    sqlite3 development_newsite.sqlite3

    SQLite version 3.7.2
    Enter ".help" for instructions
    Enter SQL statements terminated with a ";"
    sqlite>
```
输入.help查看帮助， .quit退出页面

如果需要图形界面可以安装sqlitebrowser

```bash
    sudo apt-get install sqlitebrowser
```