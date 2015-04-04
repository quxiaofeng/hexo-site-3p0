title: 零基础免费个人网站搭建手册
date: 2014-09-12 14:45:00
tags: [blog, website]
category: life
---


搭建个人网站需要几个步骤。

1. 域名
2. 存储空间
3. 界面模板
4. 内容撰写

这里提供一个免费解决方案

<!--more-->

1. 免费域名：xxxxx.tk
2. 免费存储空间：GitHub
3. 开源免费界面模板与内容撰写工具：基于 Markdown 的 Jekyll
4. 免费评论托管：disqus

具体步骤
----

参考 [Projet Compromis](http://projetcompromis.tk/)。

### 0. 前期准备 ###

+ 有一个email地址可用来注册账号

### 1. 申请域名 ###

到 [http://www.dot.tk/](http://www.dot.tk/) 这个网站注册账号，并申请一个免费域名。

推荐该域名的原因是，免费的顶级域名，不是挂在其他网站下的子域名。维护要求只有每90天有25次点击。每周维持5次点击就可以，要求很简单。注册一次可以选择12个月，之后在**到期前15日内**可以再次续约域名。域名到期前会向注册帐号email地址发提醒email，完全不会错过。

### 2. 申请空间 ###

到 [GitHub](http://www.github.com) 注册一个账号，并新建一个代码库(repo)。

### 3. 挑选模板 ###

找一个jekyll模板，复制过来。 推荐可以去这个 [Jekyll 主题站](http://jekyllthemes.org/) 挑选喜欢的模板，克隆下来。

### 4. 修改配置选项并上传建站 ###

修改网站的各项配置，填写个人信息。包括： `_config.yml`, `layout` , `include` , `css` ，修改为自己喜欢的样式。并推送到 github repo。

### 5. 配置域名 ###

一方面要修改域名服务器，把解析指向 github； 另一方面，在代码库中添加 CNAME， 修改 `_config.yml` 中与域名相关的部分。

### 6. 撰写博客文章 ###

现在，在`_posts`目录下新建个文本文档开始写就可以了。文件名于要按照格式写，`yyyy-mm-dd-a-post-name-example.md`。
