---
layout      : post
tags        : [web, latex]
title       : LaTeX 向 MathML 的转换 
description : Tools, libs, research and method about translating LaTeX code to MathML code..
category: coding
comments: true
mathjax: true
date: 2013-07-11 08:53:43
---

在网页上显示数学公式一直是个难题。尽管已经有 [MathML](http://www.w3.org/Math/) 这个数学公式的 W3C 标准，但其代码的编写繁复，难以手工撰写。另一方面 LaTeX 是学术领域内数学公式编写的事实标准。所以将 LaTeX 代码转换为 MathML 代码显示，便成为一个比较好的方案。

<!--more-->

开源工具
=================================

### [MathToWeb](http://www.mathtoweb.com/cgi-bin/mathtoweb_home.pl)

> MathToWeb is a free authoring tool that converts mathematical expressions written in AMS-Latex to presentation MathML. It allows the author to write web pages in XHTML (just a strict form of HTML) containing equations in LaTeX rather than MathML, the former being considerably easier to read and write. MathToWeb can be applied to single equations or entire documents containing many hundreds of equations.

一个基于 Java 的网页写作工具。可以用 XHTML 撰写带有 LaTeX 代码的网页，然后转换。支持将AMS-Latex 代码转换为 MathML。提供 GUI 和命令行接口。

### [LaTeXMathML](https://www.maths.nottingham.ac.uk/personal/drw/lm.html)

当前有两个活跃分支：

+ [A Brief Description of LaTeXMathML](http://math.etsu.edu/LaTeXMathML/) by [Jeff Knisley](https://sites.google.com/site/drjknisley/)

+ [The LaTeXMathML Perl Port](http://pillars.che.pitt.edu/LaTeXMathML/) by [Peter Williams](mailto:broadway@city-net.com)

标准
=============

### [MathML](http://www.w3.org/Math/)

可以在该标准网站找到使用该标准的[软件列表](http://www.w3.org/Math/Software/)，其中有一个[代码转换软件列表](http://www.w3.org/Math/Software/mathml_software_cat_converters.html)。

研究资料
============

+ [MathML 与 LaTeX 的映射关系分析](http://www.ibm.com/developerworks/cn/xml/x-mathml2/)

+ [架構於 MathML並支援LaTeX 輸入之數學討論版設計](https://github.com/quxiaofeng/csxfqu/raw/master/images/latex2mathml.pdf) by 黃皇男, 顏佩君, 王婕

示例
============

### [FreeMind blog](http://freemind.pluskid.org/) by [Chiyuan Zhang](http://pluskid.org/)
该博客使用基于 Ruby 的工具链编译 markdown 文件，生成静态博客。同时使用 pandoc 提供 pdf 版本，效果较好。

博客中有关设置的文章：

+ [The Unbearable Madness of Static Blog Generators](http://freemind.pluskid.org/technology/the-unbearable-madness-of-static-blog-generators/)
首次配置的经历

+ [Printable Version (PDF) of this Blog](http://freemind.pluskid.org/misc/printable-version-pdf-of-this-blog/) 关于 LaTeX to MathML 的转换和 pdf 文件生成的经验

该博客作者提供了一个未完善的小工具 ([Github Repo](https://github.com/pluskid/texml))。
