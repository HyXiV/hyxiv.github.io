---
title: 日常问题
description: 全生涯问题记录
slug: mit-missing-semester-course-shell
date: 2023-05-16 15:30:00+0800
image: cover.jpg
categories:
    - debug
tags:
    - debug
---

1. 执行`apt-get update`时提示
    ````shell
    N: Repository 'http://mirrors.ustc.edu.cn/debian bullseye InRelease' changed its 'Version' value from '11.5' to '11.7'
    ````

    解决方法：
    ````shell
    apt-get update --allow-releaseinfo-change
    ````
    即可正常更新源

> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)
