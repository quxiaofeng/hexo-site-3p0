---
title: LaTeX cls 文件编写指南
date: 2015-01-23 02:27:05
tags: [writing, PolyU]
category: latex
photos:
- /images/ctan_lion_350x350.png
---

编写 LaTeX cls 文件的方法、步骤与注意事项。

<!--more-->

开发与测试使用的文件结构：

+ 目标文档。可以是 word 文件或者 pdf；也可以是目标排版的手绘图。
+ cls 文件。开发目标。
+ tex 文件。使用样例。
+ pdf 文件。编译的文档结果，用来检查效果。


基本开发步骤：

1. 撰写普通的 tex 文件，实现预想功能。与目标文档比较，修正，直到实现预想功能，与目标文档排版效果一致。
2. 在 tex 文件中，抽象功能代码为函数。在使用功能代码处，修改代码为函数应用。
3. 移动并改写功能函数到 cls 文件中。
4. 保持 tex 文件中功能相关代码与函数的联系的同时，清理代码。

