---
layout: post
title: rails中设置p3p头
date: 2011-2-2 00:00:00
category: rails
tags: rails
---

由于ie6,7的bug，无法跨iframe保存cookies，所以需要设置p3p头


```ruby
class ApplicationController < ActionController::Base
  ...
 
  before_filter  :set_p3p

  def set_p3p
    response.headers["P3P"]='CP="CAO PSA OUR"'
  end
```