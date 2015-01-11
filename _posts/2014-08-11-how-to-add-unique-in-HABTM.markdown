---
layout: post
title: “如何在HABTM中添加唯一认证”
date: 2014-08-11 20:56
categories: rails
tags: rails
---

先创建has_many_and_belongs_to_many表结构

```ruby
create_join_table :products, :categories do |t|
  t.index :product_id
  t.index :category_id
end
```

在model中添加下列代码

```ruby
class Product < ActiveRecord::Base
  has_and_belongs_to_many, -> { uniq}
end
```
