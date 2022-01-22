---
title: 维护部署在github上的hexo博客
date: 2022-01-21 19:06:48
categories: [hexo]
tags: [hexo, 维护]
excerpt: 日常维护博客的一些操作
---
### 基本环境
{% note success %}
 * windows10
 * 已安装 **[Git](https://gitforwindows.org/)** 和 **[Node.js](https://nodejs.org/en/download/)**
{% endnote %}

### 日常改动流程

博客内容改动后
1. 执行 `hexo clean && hexo g -d` 来确认更新的内容
2. 依次执行以下命令将改动推送到 GitHub
```bach
git add .
git commit -m "更新说明"
git push
```
### 在更换电脑后的操作
1. 确保电脑已经安装 **[Git](https://gitforwindows.org/)** 和 **[Node.js](https://nodejs.org/en/download/)**
2. 使用以下命令将 github 的站点源文件 clone 到本地
```bach
git clone git@github.com:username/username.git.io.git
```
3. 在 clone 下来的文件夹中执行
```bach
npm install -g hexo-cli
npm install
npm install hexo-deployer-git --save
```