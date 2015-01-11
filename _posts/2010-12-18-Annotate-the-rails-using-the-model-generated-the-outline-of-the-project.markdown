---
layout: post
title: 使用Annotate为rails项目生成model的大纲
date: 2010-12-18 00:00:00
category: rails
tags: rails gem
---

[github地址](https://github.com/ctran/annotate_models)

有时候在写代码时，想不起来当前model的字段属性了，annotate帮你忙。

annotate可以以注释的方式在你model文件的底部生成model的大纲(schema)信息

#安装

```bash
gem install annotate
```

#生成

```bash
cd /path/to/app/
annotate
```

便会生成下面的注释

```ruby
# == Schema Information
#
# Table name: users
#
#  id                   :integer(4)      not null, primary key
#  email                :string(255)     default(""), not null
#  encrypted_password   :string(128)     default(""), not null
#  username             :string(255)     not null
#  reset_password_token :string(255)
#  remember_created_at  :datetime
#  sign_in_count        :integer(4)      default(0)
#  current_sign_in_at   :datetime
#  last_sign_in_at      :datetime
#  current_sign_in_ip   :string(255)
#  last_sign_in_ip      :string(255)
#  password_salt        :string(255)
```