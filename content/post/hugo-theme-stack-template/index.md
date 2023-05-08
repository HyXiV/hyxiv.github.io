---
title: Hugo Theme Stack Starter踩坑记录
description: Hugo Theme Stack Starter教程及常见问题
slug: hugo-theme-stack-starter
date: 2023-05-01 23:00:00+0000
image: cover.jpg
categories:
    - Hugo
tags:
    - Hugo
---
一、Hugo Theme Stack Starter自动部署Github Pages教程

1. 打开[Hugo Theme Stack Starter的Github链接](https://github.com/CaiJimmy/hugo-theme-stack-starter)

2. 点击右上角的 *Use this template*，创建自己的存储库（需要为Github Pages才可以使用自动部署）
![Step 2](https://user-images.githubusercontent.com/5889006/156916624-20b2a784-f3a9-4718-aa5f-ce2a436b241f.png)

3. 建好存储库之后，从右上角新建Github Codespaces.
![Create codespace](https://user-images.githubusercontent.com/5889006/156916672-43b7b6e9-4ffb-4704-b4ba-d5ca40ffcae7.png)

4. 打开CodeSpaces，在终端中运行 `hugo server` 即可预览网页

5. 检查 `config` 文件夹中的配置文件。将`config/_default/config.toml` 中的 `baseurl` 属性的值改成你自己的Github Pages地址

6. 打开存储库的设置界面，切换到 `Actions` 部分，将最后的 `Workflow Permissions` 改为 `Read and write permissions` ，如果不修改，Github Actions自动部署时将会报错。

7. 现在你可以编辑Blog了，Github Actions会自动部署Github Pages，把你的修改体现在 网页上。

二、常见问题

1. `content/page/archives/index.md` 中的 `date` 属性：文章时间早于此 `date` ，则此文章会显示在 `Home` 及 `Archives` 栏目中，时间晚于此 `date` ，文章不会显示在 `Home` 及 `Archives` 栏目中。


> Photo by [Pawel Czerwinski](https://unsplash.com/@pawel_czerwinski) on [Unsplash](https://unsplash.com/)