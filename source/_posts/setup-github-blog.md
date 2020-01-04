---
title: 使用GitHub Page搭建个人博客
date: 2020-01-04 16:53:48
tags: [github, hexo]
categories: 指南
---

GitHub Pages可以让网站直接托管在GitHub的服务器上，更新维护网站内容很简单，用git commit + git
push即可进行维护，因为GitHub Pages就是GitHub上的一个Git代码仓库。

## GitHub.io

创建一个代码仓库，命名为sallymi.github.io  
Clone代码仓库到本地

> $ git clone <https://github.com/sallymi/sallymi.github.io>
>
> $ cd sallymi.github.io
>
> $ echo “Hello World” > index.html
>
> $ git add .
>
> $ git commit -am “Initial commit”
>
> $ git push

访问sallymi.github.io

## Hexo

### 搭建Hexo

> $ npm install -g hexo-cli
>
> $ hexo init myblog
>
> $ cd myblog
>
> $ npm install

### 运行Hexo

> $ hexo s

输出如下

> INFO Start processing
>
> INFO Hexo is running at <http://localhost:4000/>. Press Ctrl+C to stop.

浏览器访问<http://localhost:4000/> 就可以看到默认主题风格的博客了。

### 发布到GitHub Pages

在myblog/_config.yml里修改：

> deploy:
>
> type: git
>
> repo: [git@github.com](mailto:git@github.com):sallymi/sallymi.github.io.git
>
> branch: master

命令行出错的话需要安装

> $ npm install hexo-deployer-git –save

发布命令：

> $ hexo d -g

### 写文章

> $ hexo n ‘name’

### 安装Next主题

> cd myblog
>
> git clone <https://github.com/theme-next/hexo-theme-next> themes/next

### 启用主题

在_config.yml里面修改

> theme: next

### 配置Next主题

  * 选择Schema  
  
四种可以选择:

Muse, Mist, Pisces, Gemini

  * 设置语言

> language: zh-Hans

  * 设置菜单

对应字段是menu。菜单内容的设置格式是：item name: link。其中 item name
是一个名称，这个名称并不直接显示在页面上，它将用于匹配图标以及翻译。
