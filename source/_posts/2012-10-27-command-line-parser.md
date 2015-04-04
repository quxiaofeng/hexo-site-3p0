---
layout: post
tags: [cmd, qt, lib, c++]
title: "C++ Command Line Parser"
description: Resources and libraries about how to parse command line arguments. Try to make program receive standard and flexible command line arguments.
category: coding
date: 2012-10-27 19:33:33
comments: true
mathjax: false
---

Resources and libraries about how to parse command line arguments. Try to make program receive standard and flexible command line arguments.

<!--more-->

## Goal

Just like the git suite.

    git commit -asm 'new commit'    

+ Both short and long form are acceptable.    

+ Can be combined together. It is really compact and really handy to use in this form.    

## Current Example project

[AnyOption](http://www.hackorama.com/anyoption/) is used in the [example project](https://github.com/quxiaofeng/dks_software).

It is working well, and the only problem is annoying warnings of strcpy(). Because the visual studio recommends to use strcpy_s(). And also the std::cout can not be seen in Qt debug console.
Another problem is AnyOption can read options from a file with ":" separating "item:value" pairs. This kind of non-standard format is not very comfortable to use.

## Resources

+ AnyOption - C/C++ Command line and resource file option parsing   
 
  - [Home Page](http://www.hackorama.com/anyoption/)    

  - [Github Project Page](https://github.com/hackorama/AnyOption/)    

  - Latest version by hamann[hamann/AnyOption](https://github.com/hamann/AnyOption)    

+ ArgvParser - C++ class for convenient parsing of command line options  
  
  - [Home Page](http://mih.voxindeserto.de/argvparser.html)    

+ QtArg - a small C++ library based on the Qt 4 for parsing command line arguments.    

  - [Home Page](http://code.google.com/p/qtargparser/)    

  - [Download](http://qtargparser.googlecode.com/files/QtArg-1.2.1-src.zip)   
   
+ KCmdLineArgs - A class for command-line argument handling.  
  
  - [Home Page](http://api.kde.org/4.x-api/kdelibs-apidocs/kdecore/html/classKCmdLineArgs.html)    

