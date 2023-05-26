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
    ![config1](https://github.com/HyXiV/hyxiv.github.io/assets/132662822/cb8667bd-8f9b-46c1-9101-c6398b2785d1)  
    点击开始配置，进入下一步  
    ![config2](https://github.com/HyXiV/hyxiv.github.io/assets/132662822/4347bab9-a056-40af-956e-d38d31c55110)  
    从路由器将此主机设置为静态IP后点击下一步  
    ![config3](https://github.com/HyXiV/hyxiv.github.io/assets/132662822/c71f0bf6-3c25-483e-ad2a-457c4c0b4950)  
    设置用户名与密码后点击下一步  
    ![config4](https://github.com/HyXiV/hyxiv.github.io/assets/132662822/c82c3b32-2933-47c0-b6b0-042cc911df0f)  
    在路由器中将此主机设置为DNS主机，完成后点击下一步  
    ![config5](https://github.com/HyXiV/hyxiv.github.io/assets/132662822/aade529e-bac5-4924-994d-12c89be91ad2)  
    点击打开仪表盘，完成首次配置  
    
    **c. 配置DNS重写**
    
    DNS重写，即将指定域名定向至指定地址，使用此功能即可将域名指向本地IP，实现通过域名访问本地服务。
    
    


    




**二、使用域名代替IP地址访问本地服务**


    

> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)
