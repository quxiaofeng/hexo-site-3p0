---
layout: post
title: "Some Notes on Python and PyGame"
description: "A little note about Python 3D display, STL file format, and C++ Calling."
headline: 
category: coding
tags: [note, python]
date: 2014-02-25 19:28:47
comments: true
mathjax: true
---

A little note about Python 3D display, STL file format, and C++ Calling.

<!--more-->

[Python FAQ](https://docs.google.com/document/d/1jEQ4A8MCJ9Q81LgyHW0uee-IT7A0b-avQoO-VaxiDtU/edit)
--------------------------------------------------------------------------------------------------


PyGame Resources
------------


+ [Simple Starfield with Python and Pygame](http://codentronix.com/2011/04/24/simple-starfield-with-python-and-pygame/)

+ [Game Programming with Python and PyGame – Making Breakout](http://codentronix.com/2011/04/14/game-programming-with-python-and-pygame-making-breakout/)

+ [PyOpenGL](http://pyopengl.sourceforge.net/)

+ [VPython](http://vpython.org/)
VPython is the Python programming language plus a 3D graphics module called "visual" originated by David Scherer in 2000. VPython makes it easy to create navigable 3D displays and animations, even for those with limited programming experience. Because it is based on Python, it also has much to offer for experienced programmers and researchers.

+ [3D Programming in Python](http://greendalecs.wordpress.com/2012/04/21/3d-programming-in-python-part-1/)

+ [Python 3D Software](http://www.vrplumber.com/py3d.py)

+ [2D graphics rendering tutorial with PyOpenGL](http://cyrille.rossant.net/2d-graphics-rendering-tutorial-with-pyopengl/)

+ [PythonGameLibraries](https://wiki.python.org/moin/PythonGameLibraries)

+ [Albow](http://www.cosc.canterbury.ac.nz/greg.ewing/python/Albow/)
A Little Bit of Widgetry for PyGame
This is a widget set for creating a GUI using PyGame. It has been developed over the course of several PyWeek game competition entries. I am documenting and releasing it as a separate package so that others may benefit from it, and so that it will be permissible for use in future PyGame entries.

+ [PyQtGraph](http://www.pyqtgraph.org/)
**PyQtGraph** is a pure-python graphics and GUI library built on [PyQt4](http://www.riverbankcomputing.co.uk/software/pyqt/intro) / [PySide](http://www.pyside.org/) and [numpy](http://www.numpy.org/). It is intended for use in mathematics / scientific / engineering applications. Despite being written entirely in python, the library is very fast due to its heavy leverage of numpy for number crunching and [Qt's GraphicsView framework](http://doc-snapshot.qt-project.org/4.8/graphicsview.html) for fast display. PyQtGraph is distributed under the [MIT open-source license](http://www.opensource.org/licenses/mit-license.php). 

[TVTK](http://docs.enthought.com/mayavi/tvtk/) STL Reader and Writer
--------------------------------------------------------------------

+ This package is based on [VTK](http://www.vtk.org/).
The **Visualization Toolkit (VTK)** is an open-source, freely available software system for 3D computer graphics, image processing and visualization. VTK consists of a C++ class library and several interpreted interface layers including Tcl/Tk, Java, and Python. Kitware, whose team created and continues to extend the toolkit, offers professional support and consulting services for VTK. VTK supports a wide variety of visualization algorithms including: scalar, vector, tensor, texture, and volumetric methods; and advanced modeling techniques such as: implicit modeling, polygon reduction, mesh smoothing, cutting, contouring, and Delaunay triangulation. VTK has an extensive information visualization framework, has a suite of 3D interaction widgets, supports parallel processing, and integrates with various databases on GUI toolkits such as Qt and Tk. VTK is cross-platform and runs on Linux, Windows, Mac and Unix platforms. 

+ [TVTK-三维可视化数据](http://sebug.net/paper/books/scipydoc/tvtk_intro.html)

+ [The MayaVi Data Visualizer](http://mayavi.sourceforge.net/)

+ [3D visualization of DXF STL file using mayavi python script](http://junweihuang.info/blog/?p=347)

+ [VTK/Examples/Python/STLReader](http://www.vtk.org/Wiki/VTK/Examples/Python/STLReader)

Python 调用外部 DLL
---------------

+ [Python:使用ctypes库调用外部DLL](http://www.cnblogs.com/wuchang/archive/2010/04/04/1704456.html)
详细的例子和流程

+ 最简ctypes实例（只能调用DLL文件中的C函数，不能调用C++类内成员函数）

    from ctypes import *
    user32 = windll.LoadLibrary('user32.dll') # load dll
    user32.MessageBoxA(0, 'Ctypes is cool!', 'Ctypes', 0)
    # call message box function

+ [**You cannot call C++ instance methods from ctypes**. You will need to export a non-member function that will call the method. It will look like this in C++...](http://stackoverflow.com/questions/19636210/accessing-ctypes-returned-objects-methods)

+ 对于 C 函数 DLL 来说，不知道头文件也是可以调用的

  1. 用微软 depends 工具，查询到函数名称。

  2. 手动编写函数输入输出参数格式，然后调用

    from ctypes import *

    pdi = cdll.LoadLibrary(r'PDI.dll') # load dll
    DiscoverCnx=getattr(pdi, "?DiscoverCnx@CPDIdev@@UAE?AW4ePiCommType@@H@Z")
    DiscoverCnx.argtypes=[c_void_p];
    DiscoverCnx.restype=c_int;
    print DiscoverCnx(c_void_p(0))

**可惜** 类成员函数调用类内成员变量或函数会造成访问越界。

HOPE - A solution to call C++ member function from Python
---------------------------------------------------------

### [boost](http://www.boost.org/) ###

+ [Exposing Classes](http://www.boost.org/doc/libs/1_55_0/libs/python/doc/tutorial/doc/html/python/exposing.html)

#### Rewrite the .h file to a Python Class ####

Consider a C++ class/struct that we want to expose to Python:

    struct World
    {
        void set(std::string msg) { this->msg = msg; }
        std::string greet() { return msg; }
        std::string msg;
    };

We can expose this to Python by writing a corresponding Boost.Python C++ Wrapper:

    #include <boost/python.hpp>

    using namespace boost::python;

    BOOST_PYTHON_MODULE(hello)
    {
        class_<World>("World")
            .def("greet", &World::greet)
            .def("set", &World::set)
        ;
    }

Here, we wrote a C++ class wrapper that exposes the member functions greet and set. Now, after building our module as a shared library, we may use our class World in Python. Here's a sample Python session:

    >>> import hello
    >>> planet = hello.World()
    >>> planet.set('howdy')
    >>> planet.greet()
    'howdy'

### [Boost.Python](http://www.boost.org/doc/libs/1_55_0/libs/python/doc/index.html) ###
This is the actual package responsible for the interoperability between C++ and Python

### [SWIG](http://www.swig.org/) ###

SWIG is another possible solution. Maybe later.