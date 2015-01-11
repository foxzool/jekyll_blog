---
layout: post
title: 生产环境下rake db:migrate报错database is not configured
date: 2010-12-17 00:00:00
category: rails
tags: rails fixerror
---

我在服务器上运行了下面的命令

```bash
    RAILS_ENV=production rake db:migrate
```
结果报错

```bash
> ** Invoke db:migrate (first_time)

> ** Invoke environment (first_time)

> ** Execute environment

> rake aborted!

> proudction database is not configured
```
google后得到解决方法,将RAILS_ENV参数放到最后

```bash
    rake db:migrate RAILS_ENV=production
```