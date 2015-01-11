---
layout: post
title: 使用sitemap_generator来为rails网站生成Sitemap
date: 2010-12-18 00:00:00
category: rails
tags: rails gem
---



[github地址](https://github.com/kjvarga/sitemap_generator)

sitemap描述了网站的页面架构，请看 [维基百科](http://zh.wikipedia.org/zh-cn/Sitemap)

* 安装

编辑Gemfile

```bash
gem 'sitemap_generator'
```

bundle install安装完成之后, 执行

```bash
rake sitemap:install
```

会在config目录下生成sitemap.rb

*配置

将SitemapGenerator::Sitemap.default_host = “http://www.example.com”里的url改为自己的网站url

通过下列方法，可以将所有文章生成出去

```bash
Post.all.each do |a|
    sitemap.add post_path(a), :lastmod => a.updated_at
  end
```

*生成

在crontab定时器里运行下列命令

```bash
rake sitemap:refresh
```
就会生成sitemap并且向搜索引擎进行提交

更多配置，请看 [文档]
