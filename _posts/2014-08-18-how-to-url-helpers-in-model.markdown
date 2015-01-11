---
layout: post
title: "如何在model中使用url_helpers"
date: 2014-08-18 22:13
categories: rails
tags: rails
---

如果想在model中使用类似 url_path 这样的helper方法， 可以这样：

```ruby
class User < ActiveRecord::Base

  include Rails.application.routes.url_helpers
  .....
  def base_url
  	 user_path(self)
  end
  
  end
```
