---
title: MIT-Missing-Semester:01-课程概览与shell
description: MIT-Missing-Semester:01-课程概览与shell学习笔记与课后习题
slug: mit-missing-semester-course-shell
date: 2023-05-16 15:30:00+0800
image: cover.jpg
categories:
    - MIT-Missing-Semester
tags:
    - MIT-Missing-Semester
    - shell
---
**一、01-课程概览与shell笔记**

1. [中文版课程网站](https://missing-semester-cn.github.io/2020/course-shell/)

**二、课后习题**

1. 输入
    ````shell
    echo $SHELL
    ````
    输出
    ````
    /bin/bash
    ````

2. 
    ````shell
    cd /tmp
    mkdir missing
    ````

3. 
    ````shell
    man touch
    ````

4. 
    ````shell
    cd missing
    touch semester
    ````

5. 
    ````shell
    echo '#!/bin/sh' > semester
    echo curl --head --silent https://missing.csail.mit.edu >> semester
    ````
    第一行中有特殊符号存在`#`以及`!`存在，需将此行包含在`'`之内。

6.
    ````shell
    ./semester
    ````
    输出
    ````shell
    -bash: ./semester: Permission denied
    ````

    输入
    ````shell
    ls -l
    ````
    输出
    ````shell
    -rw-r--r--. 1 root root 61 May 16 05:16 semester
    ````

    由`-rw-r--r--`可知，所有者权限为`rw-`，即可读/可写/不可执行；用户组权限为`r--`，即可读/不可写/不可执行；其他所有人权限为`r--`，即可读/不可写/不可执行。所有用户均无执行权限，故无法执行。

7. 
    ````shell
    man chmod
    ````

8. 
    查阅chmod文档可知，使用以下命令为当前用户`u`添加`semester`文件的执行权限`x`并执行该文件
    ````shell
    chmod u+x semester
    ./semester
    ````
未完待续



> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)
