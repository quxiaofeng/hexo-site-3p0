---
layout: post
tags: [coding, ruby]
title: Ruby Directory_watcher
description: Useful directory wather to automatically compile or generate object files.
category: coding
date: 2012-09-26 19:57:34
comments: true
mathjax: true
---

Useful directory wather to automatically compile or generate object files.

<!--more-->

## Install Ruby Gem


    gem install directory_watcher


## [Doc Online](http://codeforpeople.rubyforge.org/directory_watcher/classes/DirectoryWatcher.html)

## [Source Online](https://github.com/TwP/directory_watcher)

## Pandoc Build Daemon Script

    require 'directory_watcher'

    dw = DirectoryWatcher.new '.', :pre_load => true
    dw.glob = '*.md'
    dw.add_observer {|*args| args.each {|event| puts event}}

    dw.start
    gets      # when the user hits "enter" the script will terminate
    dw.stop

