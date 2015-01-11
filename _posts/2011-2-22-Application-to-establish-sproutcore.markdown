---
layout: post
title: 建立sproutcore应用
date: 2011-2-22 00:00:00
category: ruby
tags: javascript gem
---

sproutcore是通过rubygems来安装的

```bash
gem install sproutcore
```

建立应用

```bash
sc-init HelloWorld
```

启动应用

```bash
cd HelloWorld
sc-server
```

便会通过启动thin在locahost:4020提供应用服务