---
layout: post
title: "Enthought Canopy 1.3.0 Welcome Issue"
description: "A small issue had to be solved before running of the canopy bundle."
headline: 
category: coding
tags: [note, python, canopy]
comments: true
mathjax: false
date: 2014-02-27 15:28:32
photos:
- http://i.imgur.com/uBRhLVa.jpg
---

The Issue
---------
After a fresh install of Enthought Canopy 1.3.0.1715 win x86 version, it starts with a welcome error.

<!--more-->

<figure>
  <img src="http://i.imgur.com/hRgTP0u.png">
  <figcaption>
  The error page
  </figcaption>
</figure>

The Solution
------------
A possible solution is mentioned on the enthought blog in a reply of this post.

<figure>
  <img src="http://i.imgur.com/EgSIULO.png">
  <figcaption>
  The reply about the solution
  </figcaption>
</figure>

The solution is to change the code in file

    C:\Program Files\Enthought\Canopy32\App\appdata\canopy-1.3.0.1715.win-x86\Lib\mimetypes.py

**from**

    254    i += 1
    255
    256    default_encoding = sys.getdefaultencoding()

**to**

    254    i += 1
    255
    256    if sys.getdefaultencoding()!='gbk':
    257        reload(sys)
    258        sys.setdefaultencoding('gbk')
    259
    260    default_encoding = sys.getdefaultencoding()

It Works
--------

<figure>
  <img src="http://i.imgur.com/uBRhLVa.jpg">
  <figcaption>
  The fixed welcoming page
  </figcaption>
</figure>

I am still inexperienced to know why this solution works.

However, from the code, it can be found that the windows xp doesn't provide a proper return string 'gbk'. In the solution, the system default encoding is set manually to 'gbk'.

The problem could be the system - windows xp, but also could be the python function, which provides the system settings.