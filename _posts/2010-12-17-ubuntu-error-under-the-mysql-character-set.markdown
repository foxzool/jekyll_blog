---
layout: post
title: ubuntu下mysql字符集设置错误
date: 2010-12-17 00:00:00
category: how
tags: ubuntu mysql fixerror
---

原来在rhel下设置了

```bash
    character-set-server = utf8
```

但在ubuntu下不起作用，报错:

```bash
    mysql: unknown variable 'character-set-server=utf8'
```

换为以下设置解决问题:

```bash
    default-character-set = utf8
```
