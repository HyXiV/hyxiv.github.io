---
title: 本地局域网使用域名访问及启用HTTPS
description: 在局域网中使用域名代替IP地址访问及使用安全HTTPS的方法
slug: local-domain-and-https
date: 2023-05-26 15:30:00+0800
image: cover.jpg
categories:
    - MIT-Missing-Semester
tags:
    - MIT-Missing-Semester
    - shell
---
# **一、使用域名代替IP地址访问本地服务**
1. 为了使客户端在访问域名时指向本地服务，需在本地搭建DNS服务器，这里我们使用ADguard Home作为本地网络的全局DNS服务器，这里我们在一台debian虚拟机上安装，具体过程如下：

    **a.安装ADguard Home**  

    运行
    ````shell
    curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
    ````
    输出如下（为保护隐私IP地址已修改）
    ````shell
    AdGuard Home is now available at the following addresses:
    2023/05/25 21:33:02 [info] go to http://127.0.0.1:3000
    2023/05/25 21:33:02 [info] go to http://[::1]:3000
    2023/05/25 21:33:02 [info] go to http://111.111.111.111:3000
    2023/05/25 21:33:02 [info] go to http://[fe80:fe80:fe80:fe80:fe80:fe80%eth0]:3000
    2023/05/25 21:33:02 [info] go to http://172.172.172.172:3000
    2023/05/25 21:33:02 [info] go to http://[2606:2606:2606:2606:2606:2606:2606:2606]:3000
    2023/05/25 21:33:02 [info] service: action install has been done successfully on linux-systemd
    AdGuard Home is now installed and running
    you can control the service status with the following commands:
    sudo /opt/AdGuardHome/AdGuardHome -s start|stop|restart|status|install|uninstall
    ````
    则代表安装已经完成

    **b. 配置ADguard Home**  

    打开其中一个链接，如111.111.111.111:3000  
    会出现以下界面：  
    点击开始配置，进入下一步  
    




**二、使用域名代替IP地址访问本地服务**

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
