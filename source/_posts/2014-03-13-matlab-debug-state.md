---
layout: post
title: "Matlab Debug State Checking"
description: 
headline: 
category: coding
tags: [matlab, research, testing]
date: 2014-03-13 14:36:25
comments: true
mathjax: true
---

[GitHub Repo - balance/CheckDebug](https://github.com/quxiaofeng/balance/tree/master/DebugStatus)
----------------------------------------------------------------------------

<!--more-->

Refactor according to [the matlab style guide](http://www.quxiaofeng.me/articles/matlab-coding-style/)
------------------------------------------------------------------------------------------------------

### 函数名 ###

1. matlab 函数名一般使用小写
这里不是所有人都同意。matlab 内置函数一般使用小写，第三方程序有时使用混合大小写。但这里在使用时还是感觉全小写比较方便，混合大小写打字不方便，也容易记错。

2. 返回值是**逻辑变量**，名称使用 *is*。
所以把函数名从``CheckDebugState``为 ``isdebugging``。

### 单元测试 ###

1. 添加基本的测试： ``1, true,  'debug',   'test', 0, false, 'release', 'run'``

2. 添加后向兼容测试： ``CheckDebugState``

3. 添加例程测试，测试例程输出与标准输出

### 使用方法 / 例程 ###

1. 添加了一个简单的显示是否在调试状态的函数，作为使用该函数的例子
2. 使用`evalc`将例程打印输出转向到字符串，并保存。`fileread`读入文本文件，并比较结果。这种方法能比较程序输出，易于用来编写测试。

当前完成的函数
-------

<pre><code class="matlab">
function [ debug_state ] = isdebugging( debug_state )
% isdebugging Check debug status to determine if it is debugging.
%    debug_state = isdebugging(debug_state) parse a general debug
%    description (a number, text, or a logical values) to a 
%    standard logical value.
% 
% 
%    It returns true (in a debugging state) if the input is
%       1, true, 'debug', 'test'.
%    It returns false (in a non-debugging state) if the input is
%       0, false, 'release', 'run'.
%    Default (blank) input leads to false. (Not debugging)
% 
% 
%    After using this function, debug related code in scripts and functions
%    can be simply surrounded by
% 
%        if debugState
%            ...
%        end
% 
% 
%    In addition, the function using isdebugging can be formatted as
% 
%         function displaydebugstate(vars, debugState)
% 
%         debugState = isdebugging( debugState );
% 
%         if debugState
%             display 'debugging';
%             result = 'debugging';
%         else
%             result = 'running';
%         end
% 
%         display(result);
% 
%         end
% 
%    For more information, see <a href="matlab:
%    web('https://github.com/quxiaofeng/balance')">balance</a>.


if nargin == 1
    switch debug_state
        case 1
            debug_state = true;
        case 0
            debug_state = false;
        case true
            debug_state = true;
        case false
            debug_state = false;
        case 'debug'
            debug_state = true;
        case 'release'
            debug_state = false;
        case 'test'
            debug_state = true;
        case 'run'
            debug_state = false;
        otherwise
            display(['wrong debugflag(' ...
                '1, true,  ''debug'',   ''test'', ' ...
                '0, false, ''release'', ''run''   ',...
                ')']);
            debug_state = false;
    end
else
    debug_state = false;
end

end
</code></pre>