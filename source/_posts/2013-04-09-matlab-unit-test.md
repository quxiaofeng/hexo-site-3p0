---
layout      : post
tags        : [matlab, coding, testing]
title       : MATLAB Unit Test / MATLAB 单元测试
description : Classes, How-tos and Examples.
category: coding
date: 2013-04-09 02:33:48
comments: true
mathjax: true
---

Classes, How-tos and Examples.

<!--more-->

Update History
--------------

### R2013a ###

First introduced

>+ `matlab.unittest`  package, an xUnit-style testing framework for the MATLAB language that allows writing and running unit tests, and analyzing test results
>
>    [New MATLAB Unit Testing Framework](http://www.mathworks.com/support/2014a/matlab/8.3/demos/matlab-unit-test-framework-in-release-2013a.html) (9 min, 24 sec)
>
>    For information about the matlab.unittest package, see [Unit Testing Framework](http://www.mathworks.com/help/releases/R2013a/matlab/matlab-unit-test-framework.html).

### R2013b ###

Updated

>+ Functions for writing, executing, and verifying tests using the `matlab.unittest` testing framework without creating custom classes
> 
>    As an alternative to writing object-oriented tests, the MATLAB xUnit-style testing framework now provides function-based writing, execution, and verification of tests. For more information, see [Unit Testing Framework](http://www.mathworks.com/help/releases/R2013b/matlab/matlab-unit-test-framework.html). For an example of function–based test writing, see [Write Simple Test Case Using Functions](http://www.mathworks.com/help/releases/R2013b/matlab/matlab_prog/write-simple-test-case-with-functions.html).
> 
>+ New fixture and plugin features for `matlab.unittest` testing framework
> 
>    The `matlab.unittest` testing framework now provides four customized fixtures to ease the creation of setup and teardown code. You can use these fixtures to change the current working folder, add a folder to the MATLAB path, suppress the display of warnings, and create a temporary folder. For more information, see [`matlab.unittest.fixtures`](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.fixtures.html).
>   
>    To share these fixtures across test classes, use the new SharedTestFixtures class attribute of [TestCase](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.testcaseclass.html). The [getSharedTestFixtures](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.testcase.getsharedtestfixtures.html) method of [TestCase](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.testcaseclass.html) provides access to the shared fixtures. You also can use fixtures within a test function by calling the [applyFixture](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.testcase.applyfixture.html) method of [TestCase](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.testcaseclass.html).
>   
>    To pause execution of a test and enter debug mode upon a failure or uncaught error, you can add the new plugin, [StopOnFailuresPlugin](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.plugins.stoponfailurespluginclass.html) to the test runner. For more information, see [`matlab.unittest.plugins`](http://www.mathworks.com/help/releases/R2013b/matlab/ref/matlab.unittest.plugins.html).

### R2014a ###

Improved

>+ Custom plugins in unit testing framework
>
>    The `matlab.unittest` testing framework provides an interface class, [`matlab.unittest.plugins.TestRunnerPlugin`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.testrunnerplugin-class.html), to create custom plugins and extend the `TestRunner`. For more information, see [Write Plugins to Extend TestRunner](http://www.mathworks.com/help/matlab/matlab_prog/write-plugins-to-extend-testrunner.html) and [Create Custom Plugin](http://www.mathworks.com/help/matlab/matlab_prog/create-custom-plugin.html).
>
>+ Test parameterization and selection in unit testing framework
>
>    Test authors can write tests that are parameterized to combine and execute over lists of data. For more information, see [Create Basic Parameterized Test](http://www.mathworks.com/help/matlab/matlab_prog/create-basic-parameterized-test.html) and [Create Advanced Parameterized Test](http://www.mathworks.com/help/matlab/matlab_prog/create-advanced-parameterized-test.html).
>
>    The [`matlab.unittest.TestSuite.selectIf` ](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testsuite.selectif.html)method, combined with classes in the [`matlab.unittest.selectors`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.selectors.html) package, allows for the improved selection of tests included in the test suite.
>  
>+ `matlab.unittest` plugin for Test Anything Protocol (TAP) output
>
>    The `matlab.unittest` testing framework provides a plugin that produces a Test Anything Protocol (TAP) stream. This plugin allows integration of MATLAB unit test results into third-party systems that recognize the Test Anything Protocol such as continuous integration systems. For more information, see the [`matlab.unittest.plugins.TAPPlugin`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.tapplugin-class.html) documentation.
>
>+ Output stream direction for `matlab.unittest` plugins
>
>    The `matlab.unittest` testing framework provides a means to redirect text output from several plugins to standard output ([ToStandardOutput](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.tostandardoutput-class.html)) or to a file ([ToFile](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.tofile-class.html)). Output stream direction is supported for the [DiagnosticsValidationPlugin](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.diagnosticsvalidationplugin-class.html), [FailureDiagnosticsPlugin](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.failurediagnosticsplugin-class.html), [TAPPlugin](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.tapplugin-class.html), and [TestSuiteProgressPlugin](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.testsuiteprogressplugin-class.html) plugins.
>
>    Additionally, the [`OutputStream`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.outputstream-class.html) class provides an interface for test authors to create custom output streams.
>
>+ Comparator for MATLAB objects in unit testing framework
>
>    The [PublicPropertyComparator](http://www.mathworks.com/help/matlab/ref/matlab.unittest.constraints.publicpropertycomparator-class.html) can be used with the [IsEqualTo](http://www.mathworks.com/help/matlab/ref/matlab.unittest.constraints.isequalto-class.html) constraint to compare public properties of MATLAB objects recursively.
>+ `isdiag`, `isbanded`, `issymmetric`, `ishermitian`, `istril`, `istriu`, and `bandwidth` functions for testing matrix structure
>
>    The following functions test various aspects of matrix structure and are useful in simplifying numerical algorithms.
>  + [`ishermitian`](http://www.mathworks.com/help/matlab/ref/ishermitian.html) determines if a matrix is Hermitian or skew-Hermitian.
>  + [`issymmetric`](http://www.mathworks.com/help/matlab/ref/issymmetric.html) determines if a matrix is symmetric or skew-symmetric.
>  + [`istriu`](http://www.mathworks.com/help/matlab/ref/istriu.html) determines if a matrix is upper-triangular.
>  + [`istril`](http://www.mathworks.com/help/matlab/ref/istril.html) determines if a matrix is lower-triangular.
>  + [`isdiag`](http://www.mathworks.com/help/matlab/ref/isdiag.html) determines if a matrix is diagonal.
>  + [`bandwidth`](http://www.mathworks.com/help/matlab/ref/bandwidth.html) returns the upper and lower bandwidth of a matrix.
>  + [`isbanded`](http://www.mathworks.com/help/matlab/ref/isbanded.html) determines if a matrix is within the specified upper and lower bandwidths.

[Unit Testing Framework](http://www.mathworks.com/help/matlab/matlab-unit-test-framework.html) 单元测试框架
-----------------------------------------------------------------------------------------------------


Write and run tests for MATLAB® programs  
为MATLAB程序编写和运行测试

+ [Write Unit Tests](http://www.mathworks.com/help/matlab/write-unit-tests.html) 编写单元测试  
Assemble test methods into test-case classes  
将各个测试方法组合成测试用例类

+ [Run Unit Tests](http://www.mathworks.com/help/matlab/run-unit-tests.html) 运行单元测试  
Run test suites in the testing framework  
在测试框架中运行测试用例集

+ [Analyze Test Results](http://www.mathworks.com/help/matlab/analyze-test-results.html) 分析测试结果  
Use test results to identify failures  
使用测试结果来分析程序

[Write Unit Tests 编写单元测试](http://www.mathworks.com/help/matlab/write-unit-tests-1.html)
-------------------------------------------------------------------------------------  

Assemble test methods into test-case classes  
将各个测试方法组合成测试用例类 

The _matlab.unittest_ package is an xUnit-style, unit-testing framework for MATLAB®. To test a MATLAB program, write a test case using qualifications, which are methods for testing values and responding to failures. The test case contains test functions and test fixtures (setup and teardown code).  
_matlab.unittest_包是xUnit风格的matlab程序测试框架。

### Functions 函数 ###

>+ [`functiontests`](http://www.mathworks.com/help/matlab/ref/functiontests.html)
>    + Create array of tests from handles to local functions
>    + 使用局部函数指针生成测试组

### Classes 类   
>+ [`matlab.unittest.TestCase`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testcaseclass.html)
>    + Superclass of all _matlab.unittest_ test classes 
>    + 所有_matlab.unittest_测试类的基类

### Packages 包 ###

> + [`matlab.unittest` ](http://www.mathworks.com/help/matlab/ref/matlab.unittest.html)
>    + Summary of packages and classes in MATLAB Unit Test Framework   
>    + MATLAB 单元测试框架类函数包和函数类的集合   
>+ [`matlab.unittest.constraints`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.constraints.html)
>    + Summary of classes in MATLAB Constraints Interface  
>    + MATLAB 限制（验证）接口函数类的集合（验证各种限制条件的函数类）  
>+ [`matlab.unittest.diagnostics`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.diagnostics.html)
>    + Summary of classes in MATLAB Diagnostics Interface  
>    + MATLAB 诊断接口函数类的集合（测试失败时用来诊断的函数类）  
>+ [`matlab.unittest.fixtures`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.fixtures.html)
>    + Summary of classes in MATLAB Fixtures Interface  
>    + MATLAB 环境接口函数类的集合（准备和清理测试环境的函数类）
>+ [`matlab.unittest.qualifications`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.qualifications.html)
>    + Summary of classes in MATLAB Qualifications Interface  
>    + MATLAB 资格（验证）接口函数类（测试例外处理的函数类）

[Run Unit Tests 运行单元测试](http://www.mathworks.com/help/matlab/run-unit-tests-1.html)
--------------

Run test suites in the testing framework
在测试框架下运行测试套件

### Functions 函数 ###

>+ [`runtests`](http://www.mathworks.com/help/matlab/ref/runtests.html)
>    + Run set of tests
>    + 运行测试用例集
>+ [`matlab.unittest.TestCase.run`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testcase.run.html)
>    + Run TestCase test
>    + 运行 TestCase 测试用例
>+ [`matlab.unittest.TestSuite.run`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testsuite.run.html)
>    + Run TestSuite array using TestRunner object configured for text output
>    + 使用带有文本输出配置的 TestRunner 运行 TestSuite 测试用例组
>+ [`matlab.unittest.TestRunner.run`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testrunner.run.html)
>    + Run all tests in TestSuite array
>    + 运行 TestSuite 组中的所有测试用例
>+ [`matlab.unittest.TestRunner.addPlugin`](http://www.mathworks.com/help/matlab/ref/functiontests.html)
>    + Add plugin to TestRunner object
>    + 向 TestRunner 对象中添加插件

### Classes 类

>+ [`matlab.unittest.TestSuite`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testsuite-class.html) 
>    + Class for grouping tests to run
>    + 运行测试用例组
>+ [`matlab.unittest.Test`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.test-class.html) 
>    + Specification of a single test method
>    + 单独的测试方法函数定义
>+ [`matlab.unittest.TestRunner`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testrunner-class.html) 
>    + Class for running tests in `matlab.unittest` framework
>    + 运行 `matlab.unittest` 单元测试的框架类

### Packages 包 ###

> + [`matlab.unittest.parameters`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.parameters.html)
>    + Summary of classes associated with MATLAB Unit Test parameters  
>    + MATLAB 单元测试参数函数类集合
>+ [`matlab.unittest.plugins`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.html)
>    + Summary of classes in MATLAB Plugins Interface
>    + MATLAB 插件接口函数类集合 
>+ [`matlab.unittest.plugins.plugindata`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.plugins.plugindata.html)
>    + Summary of classes in MATLAB Plugin Data Interface
>    + MATLAB 插件数据接口函数类集合
>+ [`matlab.unittest.selectors`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.selectors.html)
>    + Summary of classes in MATLAB Selectors Interface
>    + MATLAB 筛选接口函数类集合  

[Analyze Test Results 分析测试结果](http://www.mathworks.com/help/matlab/analyze-test-results-1.html)
--------------

Use test results to identify failures
使用测试结果来鉴定出错原因

### Classes 类

>+ [`matlab.unittest.TestResult`](http://www.mathworks.com/help/matlab/ref/matlab.unittest.testresult-class.html) 
>    + Result of running test suite
>    + 测试用例套件的运行结果

Related Information 相关信息
--------------------------

+ <http://en.wikipedia.org/wiki/XUnit>  
+ <http://xunitpatterns.com/Four%20Phase%20Test.html>

Other Testing Resources
-----------------------

+ [Igloo - BDD Style Unit Testing for C++](http://igloo-testing.org/)

