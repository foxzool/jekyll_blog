---
layout: post
title: 生成rails项目的实体关系图
date: 2010-12-29 00:00:00
category: rails
tags: rails gem
---

实体关系图 == Entity-Relationship Diagrams 

[插件官网](http://rails-erd.rubyforge.org/)

首先安装Graphviz

```bash
% brew install cairo pango graphviz    # Homebrew on Mac OS X
% sudo port install graphviz           # Macports on Mac OS X
% sudo aptitude install graphviz       # Debian and Ubuntu
```

然后在开发环境中使用

```bash
group :development do
  gem "rails-erd"
end
```

安装

```bash
% bundle install
```

生成PDF
```bash
% rake erd
```