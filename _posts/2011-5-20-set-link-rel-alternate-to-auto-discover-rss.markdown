---
layout: post
title: 设置link标签使浏览器自动发现rss标签
date: 2011-5-20 00:00:00
category: html
tags: html
---

```html
<link rel="alternate" type="application/atom" title="ZoOL =&gt; Blog" href="http://zool.me/atom.xml" /> 
```

上述语句使得浏览器在打开我的博客时，会自动获取blog的rss地址。

另一个rss＋xml格式

```html
<link rel="alternate" type="application/rss+xml" title="ZoOL =&gt; Blog" href="http://blog.zool.it/feed.rss" /
```
