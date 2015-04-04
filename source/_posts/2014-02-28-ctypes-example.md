---
layout: post
title: "A Little ctypes Example"
description: "A simple ctypes example interfacing a windows dll to python."
headline: 
category: coding
tags: [python, c, c++, note]
date: 2014-02-28 19:27:07
comments: true
mathjax: false
---
A simple ctypes example interfacing a windows dll to python.

<!--more-->
## The ctypes package

+ [Homepage](http://starship.python.net/crew/theller/ctypes/)

“ctypes” is an advanced ffi (Foreign Function Interface) , and it has been included in the standard distribution of python since 2.5.

“ctypes allows to call functions in dlls/shared libraries and has extensive facilities to create, access and manipulate simple and complicated C data types in Python - in other words: wrap libraries in pure Python. It is even possible to implement C callback functions in pure Python.”

In essence, ctypes find the name of C functions in the dll file and execute the function code directly. It provides a very easy and effective way to call C functions from python. A simple example is shown below.

## A Simple Example


    from ctypes import *
    user32 = windll.LoadLibrary('user32.dll') # load dll
    user32.MessageBoxA(0, 'Ctypes is cool!', 'Ctypes', 0)
    # call message box function


First, the ctypes package is imported to current file. Then the user32.dll is loaded as variant user32. (user32.dll is a basic windows dynamic library. It is pre-installed in every windows operating system.) After the loading of user32 library, we can call MessageBoxA function, which is in the user32 library as an ordinary python method. The MessageBoxA pops up a message box over the desktop. The parameters defined the text and title of this message box as shown below.

<figure>
  <img src="http://i.imgur.com/EsDsYsI.png">
  <figcaption>
  Message box called by python
  </figcaption>
</figure>

In this calling process, no lower level code is need. DLL functions can be called solely by python.

However, a critical problem is that the ctypes package only supports C function or C++ function without Class feature. **It does not support C++ Class.**

## A Failed C++ Class Example

The C function name saving in the dll file is identical with one in the source file. Nevertheless, the C++ function is not. For example, a function name is “enum ePiCommType CPDIdev::DiscoverCnx(int)” in source file. In the DLL file, the function name is “?DiscoverCnx@CPDIdev@@UAE?AW4ePiCommType@@H@Z” as shown in the figure below. The ctypes package can resolve latter one as the former one. That is how it can call C functions.

<figure>
  <img src="http://i.imgur.com/O6Gc5oz.png">
  <figcaption>
  The C++ function name in the DLL file under the inspection tool
  </figcaption>
</figure>

The names of functions can be inspected by "[Dependency Walker](http://www.dependencywalker.com/)".

<figure>
  <img src="http://i.imgur.com/3I3AWXk.png">
  <figcaption>
  Dependency Walker Homepage
  </figcaption>
</figure>

In addition, the python can find the function with the help of the ctypes package in a similar way as shown below.

<figure>
  <img src="http://i.imgur.com/d0Ku9wE.png">
  <figcaption>
  Python find a function pointer in the DLL file
  </figcaption>
</figure>

The address of the function “enum ePiCommType CPDIdev::DiscoverCnx(int)” is found in 0x01D65828. However, it raised an exception when it is being called as shown below.

<figure>
  <img src="http://i.imgur.com/WluRzwI.png">
  <figcaption>
  Exception raised when called by python
  </figcaption>
</figure>

This exception is raised because the ctypes does not support C++ class. In a C++ class, the member function rewrites member variants, which are out of the range of the function. That is why the system raised an access violation exception.
