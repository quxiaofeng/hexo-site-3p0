---
layout: post
title: "A SWIG Example"
description: "A SWIG example interfacing a windows dll to python."
headline: 
category: coding
tags: [coding, python, c, c++]
comments: true
mathjax: false
date: 2014-03-01 17:58:51
---

## [SWIG](http://www.swig.org)

SWIG is stand along software development tool. It connects code programmed in C and C++ with many high-level programming languages including python. SWIG is used to parse C/C++ interfaces and generate the 'glue code' required for the above target languages to call into the C/C++ code. 

<!--more-->

The idea of SWIG is to create a dynamic python library module, which calls the SDK DLL. The structure is shown below.

<figure>
  <img src="http://i.imgur.com/rPhlR7E.png">
  <figcaption>
  SWIG interfacing principle
  </figcaption>
</figure>

The SWIG compiles the DLL and H files under the instruction of the .i file (SWIG configuring file). The SWIG project generates the Python Dynamic Library file (pyd). This pyd file can be imported to python.

## A Basic But Not Simple Example

+ [github repo](https://github.com/quxiaofeng/swig-cpp-class-dll-wrapping-test)

### 1. Make a little DLL project. ###

In the repo, this little DLL project is **xiaoAdd**. There is a **class AddTest**. This class has only one useful **member function add**.

`AddTest.h`

    /* AddTest.h */
    #pragma once

    class __declspec(dllexport) AddTest
    {
    public:
        AddTest(void);
        ~AddTest(void);
        int add(int a, int b);
    };

`AddTest.cpp`

    /* AddTest.cpp */
    #include "AddTest.h"

    AddTest::AddTest(void)
    {
    }

    AddTest::~AddTest(void)
    {
    }

    int AddTest::add(int a, int b)
    {
        return a+b;
    }

Compile this project and get the results.


    xiaoAdd.dll
    xiaoAdd.lib
    xiaoAdd.pdb


### 2. Make a Python dynamic module ###

In the github repo, this module is xiaoA

*AddTest.h*

    /* AddTest.h */
    #pragma once

    class __declspec(dllimport)AddTest
    {
    public:
        AddTest(void);
        ~AddTest(void);
        int add(int a, int b);
    };

*xiaoAddModule.i*

    /* xiaoAddModule.i */
    %module xiaoAddModule

    %{
    /* Put header files here or function declarations like below */
    #include "AddTest.h"
    %}

    %include <windows.i>
    %include "AddTest.h"

#### 1. Compile the xiaoAddModule.i for xiaoAddModule_wrap.cxx. ####
 
#### 2. Build the project ([Reference](http://stackoverflow.com/questions/11693047/how-to-create-a-dll-with-swig-from-visual-studio-2010)) including ####

    xiaoAddModule_wrap.cxx
    AddTest.h
    xiaoAdd.dll
    xiaoAdd.lib


#### 3. Get the results ####

    _xiaoAddModule.exp
    _xiaoAddModule.lib
    _xiaoAddModule.pdb
    _xiaoAddModule.pyd
    xiaoAddModule.py
    xiaoAddmodule.pyc

#### 4. Write the Python script within the folder where above results are located. ####

`test.py`

    # test.py
    import xiaoAddModule
    instance = xiaoAddModule.AddTest()
    print 'The result of 2 + 3 = %r' % (instance.add(2,3))
    wait = input("PRESS ENTER TO EXIT.")

## A Complex Solution For A Complex Example

When wrapping a complex 3rd party library, there are lots of classes and functions. We want to keep this interface nice and clean. A C++ wrapper is implemented as shown below.

<figure>
  <img src="http://i.imgur.com/lHar1Ig.png">
  <figcaption>
  Double layer wrapping
  </figcaption>
</figure>

