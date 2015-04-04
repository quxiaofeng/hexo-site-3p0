---
layout: post
title: "Matlab Coding Style"
description: "A formal, informative and elegant coding style for matlab codes."
headline: 
category: coding
tags: [matlab, coding]
comments: true
date: 2014-03-02 02:34:39
---

A formal, informative and elegant coding style for matlab codes.

<!--more-->

## Coding Style

#### Help Comment ####

    %ONE Complete help comment of function.
    %   debug_state = CheckDebugStatus(debug_state) parse a general debug
    %   description to a standard logical value.
    %
    %
    %   It returns true (in a debugging state) if the input is
    %      1, true, 'debug', 'test'.
    %   It returns false (in a non-debugging state) if the input is
    %      0, false, 'release', 'run'.
    %   Default (blank) input leads to false. (Not debugging)
    %
    %
    %   After using this function, debug related code in scripts and functions
    %   can be simply surrounded by
    %
    %       if debug_state
    %           ...
    %       end
    %
    %
    %   In addition, the function using CheckDebugStatus can be formatted as
    %
    %      function [ result ] = Test(vars, debug)
    %
    %          debug = CheckDebugStatus( debug );
    %
    %          if debug
    %              display 'debugging';
    %              result = 'debugging';
    %          else
    %              result = 'running';
    %          end
    %          display(result);
    %      end
    %
    %   For more information, see <a href="matlab:
    %   web('https://github.com/quxiaofeng/balance')">balance</a>.

## Debug State in Balance ([GitHub](https://github.com/quxiaofeng/balance))

Using this **CheckDebugState** function, the debugging code can be separated from general code.

        It returns true (in a debugging state) if the input is
            1, true, 'debug', 'test'.
        It returns false (in a non-debugging state) if the input is
            0, false, 'release', 'run'.
        Default (blank) input leads to false. (Not debugging)


    function [ result ] = Test(vars, debug)

        debug = CheckDebugStatus( debug );

        if debug
            display 'debugging';
            result = 'debugging';
        else
            result = 'running';
        end

        display(result);
    end

## Books

**Richard Johnson** has published a [book](http://www.cambridge.org/us/knowledge/isbn/item5745060/?site_locale=en_US) **"The Elements of MATLAB Style"** (also see [wiki](https://sites.google.com/site/matlabstyleguidelines/)) 2010.

<figure>
  <img src="http://i.stack.imgur.com/CpCOr.jpg">
  <figcaption>
  The Elements of MATLAB Style
  </figcaption>
</figure>

Table of Contents

1. General principles
2. Formatting
3. Naming
4. Documentation
5. Programming
6. Files and organization
7. Development

Loren has a blog entry with the [review of the book](http://blogs.mathworks.com/loren/2011/02/10/book-review-the-elements-of-matlab-style/). I will just follow here line of comments:

**7**. Split Long Code Lines at Graceful Points

I find this one useful as it is a total pain having to trail far off to the right in any editor, even though it is possible.
 
**10**. Do Not Use Hard Tabs
 
This helps keep sanity when working among a group with possibly different editing environments.
 
**43**. Use Meaningful Names for Variables with a Large Scope
 
This makes code much easier to read, understand, and debug, if necessary.
 
**69**. Name Functions for What They Do
 
Since functions perform an action, the name should include information about the action.
 
**86**. Use Sortable Numbering in Data Filesnames

If you have many similar files of data, having a rational numbering scheme can only help you out. 

**97**. Be Sure That Comments Agree with the Code
 
I will never forget the time that my thesis advisor called me because he was really irritated. I had left him a copy of a Fortran program that had copious comments, the final one being "Ignore all the comments above; they were for a previous version."
 
**135**. Avoid Cryptic Code
 
I have found that generally, writing cryptic code buys less than I expect in terms of good things, and more headaches than it warrants. On occasion, I have used cryptic code for performance in something time-critical. When I do, I try to comment it fully, including a straight-forward implementation in the comments which I have tested. That way, when the performance trade-offs change, I understand what the code is supposed to do and have two starting options for doing a code update.
 
**150**, **151**. Minimize the Use of Global Variables and Minimize the Use of Global Constants
 
I would say this even more strongly myself. There are superior techniques for dealing with information you want to share, whether they be function handles, classes and their properties, or some other methods. These techniques are much safer to use for many reasons - e.g., more easily controlled side effects, should any be desired, and code becomes more suitable for parallelism potentially.
 
**172**. Use Parenthese

Clarity of meaning is paramount, especially if others need to understand, modify, or translate the code.
 
**176**. Avoid Use of eval When Possible

I'm sure it doesn't seem so to some MATLAB users, but eval is avoidable most of the time.
 
**185**-**188**. The first of these is Avoid Complicated Conditional Expressions
 
These entries contain some useful thoughts on dealing with conditional constructs, the ordering of the cases, etc.
 
**271**-**275**. The first of these is Write Small Tests

I love that Richard has made testing a central tenet of this style guide. I don't see how programmers function well without a robust test suite.

+ [Modern MATLAB codestyle: what is missing?](http://stackoverflow.com/questions/17453244/modern-matlab-codestyle-what-is-missing) in [StackOverflow](http://stackoverflow.com/)

References
----------

+ [MATLAB Wiki](http://matlab.wikia.com/wiki/FAQ) - [GMPP](http://www.mit.edu/~pwb/cssm/GMPP.pdf)
+ [MATLAB code style guide](http://4dpiecharts.com/matlab-code-style-guide/)
+ [MATLAB Style Guide](http://www.cs.cornell.edu/courses/cs99/2002fa/matlabstyle.html)
+ [matlab tips and tricks and ...](http://www.ee.columbia.edu/~marios/matlab/matlab_tricks.html) by [marios athineos](http://www.ee.columbia.edu/~marios/)
+ [MATLAB Programming Style Guidelines](http://www.mathworks.com/matlabcentral/fileexchange/2529-matlab-programming-style-guidelines)
+ [MATLAB Tips & Tricks](http://www.mathworks.com/matlabcentral/fileexchange/5642-matlab-tips-tricks)