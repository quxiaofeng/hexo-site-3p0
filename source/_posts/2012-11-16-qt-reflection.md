---
layout : post
tags : [coding, c++, qt]
description: Explain what is reflection and how to implement reflection in Qt.
category: coding
title: Qt Reflection
date: 2012-11-16 19:32:51
comments: true
mathjax: false
---

Explain what is reflection and how to implement reflection in Qt.

<!--more-->

# Reflection 反射

定义参见wiki

+ <a href="http://zh.wikipedia.org/wiki/%E5%8F%8D%E5%B0%84_(%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%A7%91%E5%AD%A6)" title="http://zh.wikipedia.org/wiki/%E5%8F%8D%E5%B0%84_(%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%A7%91%E5%AD%A6)">反射 中文</a>
+ <a href="http://en.wikipedia.org/wiki/Reflection_(computer_programming)" title="http://en.wikipedia.org/wiki/Reflection_(computer_programming)" >Reflection in English</a>

简单说，是使用类与方法的名字的字符串，调用类和方法。

在底层(如汇编)，程序与数据都是以数据形式存储的，都是可读的(如果放在RAM也都是可写的)，所以程序可以检查、修改自身。

理论上C其实也可以修改自身。在知道程序在内存中的地址之后，以此地址声明一个指针，然后向此指针进行二进制读写。但这就是超出语言逾期的使用方法了。

# 两篇关于用Qt实现反射的帖子

+ [Reflection on Qt](http://www.qtcentre.org/threads/42006-Reflection-on-Qt)
+ [How to dynamically instantiate a class using the class name](http://qt-project.org/forums/viewthread/18786). And this is a typical example.

使用的是[QMetaType Class](http://qt-project.org/doc/qt-4.8/qmetatype.html)

# 例子

Ruby语言的例子

    # without reflection
    obj = Foo.new
    obj.hello

    # with reflection
    class_name = "Foo"
    method = :hello
    obj = Kernel.const_get(class_name).new
    obj.send method
