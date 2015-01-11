---
layout: post
title: 新建rails项目的参数设置
date: 2010-12-17 00:00:00
category: rails
tags: rails
---


#实例

```bash
    rails new newapp -d=mysql -T -J

    rails new newapp -d=postgresql -b=https://gist.github.com/611035
```

#参数
    rails new APP_PATH [options]

##APP_PATH

/path/to/appname， 不管前面是多复杂的路径，最后的appname就是新建的项目的名称

```bash
    rails new ~/Desktop/newapp  #在桌面目录上新建一个newapp目录，项目名叫newapp
```

##options

```bash
    -m, [--template=TEMPLATE]
```

用模板文件来创建项目,模板文件可以是本机文件，也可以是一个url地址

在使用模板文件创建项目时，可以按照模板文件的配置要求，生成对应的文件/目录

```bash
    [--skip-gemfile]
```

不创建Gemfile文件

```bash
    [--dev]
```

开发调试用，将项目的rails指向本地gem里的rails路径.

```bash
    -d, [--database=DATABASE]
```

选择数据库，有mysql/oracle/postgresql/sqlite3/frontbase/ibm_db几种选择,默认是sqlite3

```bash
    -O, [--skip-active-record]
```

不使用active-record

```bash
    -J, [--skip-prototype]
```

不使用prototype

```bash
    -T, [--skip-test-unit]
```

不使用prototype

```bash
    -G, [--skip-git]
```

不创建.gitnore和.keeps

```bash
    -b, [--builder=BUILDER]
```

用模板文件来创建项目,模板文件可以是本机文件，也可以是一个url地址

在使用模板文件创建项目时，可以按照模板文件的配置要求，生成对应的文件/目录

```bash
    -r, [--ruby=PATH]
```

设置运行项目的ruby路径，默认是当前环境下的ruby路径

```bash
   [--edge]
```

从github更新最新的rails版本来运行项目

##其他选项

```bash
Runtime options:

    -p, [--pretend]  # 运行脚本时不生成文件

    -q, [--quiet]    # 运行脚本时不输出信息
    -s, [--skip]     # 跳过已经存在的文件
    -f, [--force]    # 覆盖已经存在的文件

Rails options:
    -h, [--help]     # 显示帮助
    -v, [--version]  # 显示Rails版本号
```
