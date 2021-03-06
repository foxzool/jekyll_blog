---
layout: post
title: gem install mysql2 报错
date: 2010-12-17 00:00:00
category: how
tags: ruby fixerror rails
---

在服务器上安装mysql时，报错，安装失败， 内容如下

```bash
> sudo gem install mysql  
> Building native extensions.  This could take a while...   
> ERROR:  Error installing mysql:  
> ERROR: Failed to build gem native extension.  
> /usr/local/bin/ruby extconf.rb install mysql     
> checking for mysql_query() in -lmysqlclient... no      
> checking for main() in -lm... yes   
> checking for mysql_query() in -lmysqlclient... no   
> checking for main() in -lz... yes   
> checking for mysql_query() in -lmysqlclient... no   
> checking for main() in -lsocket... no   
> checking for mysql_query() in -lmysqlclient... no   
> checking for main() in -lnsl... yes   
> checking for mysql_query() in -lmysqlclient... no   
> extconf.rb failed  
> Could not create Makefile due to some reason, probably lack of   
> necessary libraries and/or headers.  Check the mkmf.log file for more   
> details.  You may need configuration options.   

> Provided configuration options:   
>    --with-opt-dir   
>    --without-opt-dir   
>    --with-opt-include   
>    --without-opt-include=${opt-dir}/include   
>    --with-opt-lib   
>    --without-opt-lib=${opt-dir}/lib   
>    --with-make-prog   
>    --without-make-prog 
>    --srcdir=. 
>    --curdir 
>    --ruby=/usr/local/bin/ruby 
>    --with-mysql-config 
>    --without-mysql-config 
>    --with-mysql-dir 
>    --without-mysql-dir   
>    --with-mysql-include   
>    --without-mysql-include=${mysql-dir}/include   
>    --with-mysql-lib   
>    --without-mysql-lib=${mysql-dir}/lib   
>    --with-mysqlclientlib   
>    --without-mysqlclientlib   
>    --with-mlib   
>    --without-mlib   
>    --with-mysqlclientlib   
>    --without-mysqlclientlib   
>    --with-zlib   
>    --without-zlib   
>    --with-mysqlclientlib   
>    --without-mysqlclientlib   
>    --with-socketlib   
>    --without-socketlib   
>    --with-mysqlclientlib   
>    --without-mysqlclientlib   
>    --with-nsllib   
>    --without-nsllib   
>    --with-mysqlclientlib   
>    --without-mysqlclientlib    
```

经检查，是由于我将mysql调整了安装目录导致， 执行下面代码后安装成功.

```bash
    sudo gem install mysql -- --with-mysql-config=/usr/local/mysql/bin/mysql_config
```