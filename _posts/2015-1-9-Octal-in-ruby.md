---
layout: post
title: ruby 中的八进制
date: 2015-1-9 22:34
categories: ruby
tags: ruby
---

* 八进制表示方式
用o代表无符号八进制

```ruby
> irb                                                                                                                                                
2.2.0 :001 > puts 0233, 0o233, 0O233
155
155
155
```
* 十进制转八进制

```ruby
> irb                                                                                                                                                
2.2.0 :001 > 233.to_s(8)
 => "351"
```
* 文本转八进制

```ruby
> irb                                                                                                                                                
2.2.0 :001 > "11".to_i(8)
 => 9
2.2.0 :002 > "11".to_i(8) == 011
 => true
```
