---
layout: post
title: ruby-新年快乐
date: 2010-12-29 00:00:00
category: ruby
tags: ruby
---

根据网上的源码改编

```ruby
 ruby -e "((1..20).to_a+[6]*4).each{|i|puts ('#'*i*2).center(80)};puts;puts 'Happy New Year'.center(80)"
```

关键是center方法
```ruby
"Happy New Year".center(80)
```
就是将字符串在80个字符的长度内居中