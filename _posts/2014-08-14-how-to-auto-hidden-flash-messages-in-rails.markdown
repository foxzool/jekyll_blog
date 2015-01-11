---
layout: post
title: “如何在rails中自动隐藏flash message消息”
date: 2014-08-14 21:46
categories: rails
tags: rails javascript
---
很简单，在`assets/javascript`加入以下 coffee script 代码

```javascript
$ ->
      flashCallback = ->
        $(".alert").fadeOut()
      $(".alert").bind 'click', (ev) =>
        $(".alert").fadeOut()
      setTimeout flashCallback, 3000
```
