---
layout: post
title: “如何在rails中使用hstore模块”
date: 2014-08-12 22:26
categories: rails
tags: rails postgresql
---

首先解释一下什么是 `hstore`

`hstore` 是 `postgresql` 自带的一个模块，可以在字段内用 key/value 格式存储文档数据。

rails4 开始已经在自带的PostgreSQLAdapter中加入了hstore的支持。使用方式如下。

```ruby
class CreateProfiles < ActiveRecord::Migration
  #启用hstore模块
  enable_extension 'hstore' unless extension_enabled?('hstore')
  def change
    create_table :profiles do |t|
      t.hstore 'settings'
      t.timestamps
    end
    #可以给hstore字段加索引，, 类型有 gin 和 gist
    add_index :profiles, :settings, using: :gin
  end
end
```

关于 `gin` 与 `gist` 索引格式的选择， 请看官方文档。

<pre>
In choosing which index type to use, GiST or GIN, consider these performance differences:

GIN index lookups are about three times faster than GiST

GIN indexes take about three times longer to build than GiST

GIN indexes are moderately slower to update than GiST indexes, but about 10 times slower if fast-update support was disabled (see Section 54.3.1 for details)

GIN indexes are two-to-three times larger than GiST indexes

As a rule of thumb, GIN indexes are best for static data because lookups are faster. For dynamic data, GiST indexes are faster to update. Specifically, GiST indexes are very good for dynamic data and fast if the number of unique words (lexemes) is under 100,000, while GIN indexes will handle 100,000+ lexemes better but are slower to update.

Note that GIN index build time can often be improved by increasing maintenance_work_mem, while GiST index build time is not sensitive to that parameter.
</pre>

`GIN` 比 `GiST` 索引快三倍，但也多花了三倍时间。

postgresql 的其他模块用法可以在[官方文档](http://edgeguides.rubyonrails.org/active_record_postgresql.html)找到

其中注意，保存完 `hstore` 字段后的数据， 如果要修改时， 需要执行`字段名_will_change!` 这个方法

```ruby
## you need to call _will_change! if you are editing the store in place
profile.settings["color"] = "green"
profile.settings_will_change!
profile.save!
```
