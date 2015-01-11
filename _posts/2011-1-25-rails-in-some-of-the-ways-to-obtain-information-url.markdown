---
layout: post
title: rails中获取url信息的一些方法
date: 2011-1-25 00:00:00
category: rails
tags: rails
---

如本机我测试域名为test.blog.zool.it:3000

打开的uri为 /post/Hello-World

fullurl为 http://test.blog.zool.it:3000/post/Hello-world

则rails的路由生成一下几个方法

#domain(tld_length = 1)
取得域名

```ruby
request.domain #=>  zool.it
request.domain(2) #=> blog.zool.it
```

#subdomain(tld_length = 1)
#subdomains(tld_length = 1)
取得子域名

```ruby
request.subdomain #=>  "test.blog"
request.subdomain(2) #=> "test"
request.subdomain #=>  ["test", "blog"]
request.subdomain(2) #=> ["test"]
```

#host()
取得主机名

```ruby
request.host #=> "test.blog.zool.it"
```

#host_with_port()
取得带端口的主机名

```ruby
request.host_with_port #=> "test.blog.zool.it:3000"
```

#raw_host_with_port()
代理服务器的主机名和端口

```ruby
request.raw_host_with_port #=> "test.blog.zool.it:3000"
```


#port()
取得由raw_host_with_port()获得的端口数值

```ruby
request.port #=> 3000
```

#port_string()
取得raw_host_with_port()获得的端口文本字符串

```ruby
request.port_string #=> ":3000"
```

#protocol()
取得当前使用网络协议

```ruby
request.protocol #=> "http://"
```

#scheme()
取得网络协议

```ruby
request.scheme #=> "http"
```



#request_uri()
request请求的uri地址

```ruby
request.request_uri #=> "/posts/Hello-World"
```
server_port

#server_port()
取得由env['SERVER_PORT']返回的端口值

``ruby
request.server_port #=> "3000"
```

#ssl?()
当前是否在是用https加密协议

```ruby
request.ssl?() #=> false
```

#standard_port()
返回网络协议标准端口(http为80, https为443)

```ruby
request.standard_port #=> 80
```

#standard_port?()
判断当前协议是否是标准端口

```ruby
request.standard_port? #=> false
```

#url()
取得当前requset完整url

```ruby
request.url #=> "http://test.blog.zool.it:3000/posts/Hello-World"
```