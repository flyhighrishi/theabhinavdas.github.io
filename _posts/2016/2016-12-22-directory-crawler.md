---
layout: post
title: Directory Crawler
description: A simple lightweight command-line application to crawl all accessible directories recursively within a target directory and output the results into a text file.
keywords: c# programming, console application, directory crawler, get directories
tags: [CSharp, Console Application, Project]
comments: true
---

> 2018-03-25 Updated to v2.0: Optimized the code and changed application type to command-line application.

Directory Crawler is a simple lightweight command-line application built in .NET C# to crawl all accessible directories within a target directory (entry point) and output the results to a text file.

I created this program because I need to monitor some shared directories within a local network.

### Screenshot

Here's how the program looked like and works, executed from Command Prompt, in animated GIF:

![DirectoryCrawler](https://i.imgur.com/Re1267D.gif)

After the program finished running, an output text file will be created within the program base folder and if you open the text file, this is how it looked like; a list of accessible directories within the target directory.

Example (opened using Notepad2-mod app):

![Output file](https://i.imgur.com/qaUZ9n3.png)

### Source Code and Downloads

The source code is available on my [GitHub](https://github.com/heiswayi/DirectoryCrawler) repository and compiled using Visual Studio 2015 Community. The source code is released under [MIT](https://heiswayi.github.io/mit-license) license. The latest binary package can be download from the [release page](https://github.com/heiswayi/DirectoryCrawler/releases).
