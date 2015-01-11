---
layout: post
title: 配置rails首页
date: 2010-12-27 00:00:00
category: rails
tags: rails
---

新建rails项目之后， 将public/index.html删除

然后，生成首页的controller

```bash
rails g controller home index
```

编辑config/routes.rb,配置root

```bash
root :to => 'home#index'
```

配置完毕， 所有到/ 的访问都转向了home控制器的index方法