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
    输入
    ````shell
    cd /tmp
    mkdir missing
    ````

3. 输入
    ````shell
    man touch
    ````

4. 输入
    ````shell
    cd missing
    touch semester
    ````

5. 输入
    ````shell
    echo '#!/bin/sh' > semester
    echo curl --head --silent https://missing.csail.mit.edu >> semester
    ````
    第一行中有特殊符号存在`#`以及`!`存在，需将此行包含在`'`之内。

6. 输入
    ````
    ./semester
    ````
    输出
    ````
    -bash: ./semester: Permission denied
    ````

    输入
    ````
    ls -l
    ````
    输出
    ````
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
    查阅[shebang](https://zh.wikipedia.org/wiki/Shebang)可知，系统根据`semester`首行的`#!/bin/sh`得知此文件使用`sh`执行。

9.
    输入
    ````shell
    ./semester | grep Last-Modified > ~/last-modified.txt 
    ````

    可以输入
    ````shell
    cat ~/last-modified.txt
    ````
    输出为
    ````shell
    Last-Modified: Sat, 06 May 2023 11:21:52 GMT
    ````

10. 
    由于本人使用VPS实现此部分练习且无Linux主机，无法完成此练习。
    

> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)
