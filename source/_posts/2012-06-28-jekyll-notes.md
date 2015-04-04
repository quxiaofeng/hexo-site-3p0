---
layout: post
tags : [jekyll, blog, ruby, python]
description: Some tips and tricks of jekyll. Windows is still not a best develop platform. I have to tweak a little to run jekyll smoothly. Here are the notes for myself, and also for other people who may encounter similar problems.
category: coding
title: Jekyll Notes
comments: true
mathjax: false
date: 2012-06-28 19:44:44
---

Some tips and tricks of jekyll. Windows is still not a best develop platform. I have to tweak a little to run jekyll smoothly. Here are the notes for myself, and also for other people who may encounter similar problems.

<!--more-->
    
### Guides

+ [Setting up the environment for jekyll](http://bradleygrainger.com/2011/09/07/how-to-use-github-pages-on-windows.html)
+ Don't forget to change code page before jekyll

    chcp 65001
    jekyll --safe
+ _debug.bat
  + change site.url to /
  + then do this

    rmdir _site /s /q
    chcp 65001
    jekyll --server
    PAUSE

+ _build.bat
  + change site.url to http://www4.comp.polyu.edu.hk/~csxfqu/
  + then do this

    rmdir _site /s /q
    chcp 65001
    jekyll --safe
    PAUSE

+ [Code highlight names](http://pygments.org/docs/lexers/)

## Steps

+ install Railsinstaller
    + gem update and install many gems ...
+ install [Python 2.7.3](http://www.python.org/getit/)
+ install [easy_install for python 2.7](http://pypi.python.org/pypi/setuptools#downloads)
  - in python273/Script forlder
  - add this folder("C:\Python27\Scripts" by default) to system PATH
+ install pygments

    easy_install pygments

### add _post_url_, the relative internal links to post   

+ follow this [guide](https://github.com/mojombo/jekyll/issues/66)    
+ download post_url.rb file [here](https://github.com/thatguystone/jekyll/blob/5cffe5ecb5194ef0e26e66ced1e2ef5285a934e7/lib/jekyll/tags/post_url.rb)    
+ the post_url.rb file should be put into this folder

---
{% raw %}
    \liquid\tags    
{% endraw %}   
---

+ the format is showed below as addressed in [this thread](https://github.com/mojombo/jekyll/pull/369)

---
{% raw %}
    Syntax: {% post_url 2012-06-28-name-of-post %}. 
    Useful for: [Some Link]({% post_url 2012-06-28-name-of-post %}) 
{% endraw %}
---

+ And due to the relative-pathing of my blog, the actual link should be like this

---
{% raw %}
    [example to this post]({{ site.url }}{% post_url 2012-06-28-jekyll-notes %})
{% endraw %}
---

### [Liquid guide](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)

+ And the [patch](http://bradleygrainger.com/2011/09/07/how-to-use-github-pages-on-windows.html) under windows

### Bibtex Citation

+ [Jekyll-citation](https://github.com/archome/jekyll-citation)
+ [Jekyll-Scholar](https://github.com/inukshuk/jekyll-scholar)



