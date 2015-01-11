---
layout: post
title: rails3rc1在安装rspec-rails时碰到报错
date: 2011-5-23 00:00:00
category: rails
tags: rails fixerror
---

#今天在rails3rc1下安装rspec-rails, 提示了以下错误

```bash
Invalid gemspec in [/Users/ZoOL/.rvm/gems/ruby-1.8.7-p334/specifications/rspec-core-2.6.2.gemspec]: invalid date format in specification: "2011-05-21 00:00:00.000000000Z"
```

#解决方法

找到specifications/rspec-core-2.6.2.gemspec， 将下面这行注释

```bash
s.date = %q{2011-05-21 00:00:00.000000000Z}
```

#另外在执行rake命令时， 遇到了下面的报错信息

```bash
undefined method `prerequisites' for nil:NilClass
```

google后发现是rspec-rails版本的问题， 使用2.6.1.beta1版本以上就好了， 编辑Gemfile

```ruby
  gem 'rspec-rails', '~> 2.6.1.beta'
```