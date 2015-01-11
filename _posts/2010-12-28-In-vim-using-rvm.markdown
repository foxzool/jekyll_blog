---
layout: post
title: 在vim中使用rvm
date: 2010-12-28 00:00:00
category: misc
tags: vim rvm
---


[github地址](https://github.com/csexton/rvm.vim)


将plugin下载到你的vim plugin里

```bash
curl http://github.com/csexton/rvm.vim/raw/master/plugin/rvm.vim > ~/.vim/plugin/rvm.vim
```

编辑vimrc，加入下面的代码

```bash
set statusline+=%{exists('g:loaded_rvm')?rvm#statusline():''} 
```