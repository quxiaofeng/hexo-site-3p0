---
layout: post
title: 一次失败的积分 A failed Integration
date: 2017-01-06 19:53:38
tags: [python, programming, math]
category: coding
description: 
headline: 
comments: true
mathjax: true
photos:
---

Recently, there is a funny photo circulates in the WeChat.

![Integration for Wi-Fi password](/images/integral-wifi-password.jpg)

As one can see, the integration is complicated, and it really got me. I have contacted two other friends for advice. However, we both lost the ability to compute this integration manually.

I tried with `Sympy` in `IPython`. Still, we got no answer.

Finally, one of my colleges told me that it obviously is zero. Because the function to be integrated is an odd function and the limits are symmetric.

I drew all functions from basics with SymPy and IPython. They all make sense. Only the integration can not be done.

The calculation in the github: http://nbviewer.jupyter.org/github/quxiaofeng/quxiaofeng.github.io/blob/master/ipynb/WiFi-pass.ipynb