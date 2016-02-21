---
title: Build This Blog
date: 2016-02-18 11:09:12
tags: [node,git,travis,hexo]
categories: 其它
toc: true
---

# 虽然有点迟，不过总归是开始了

## 部署

如果没有node环境，最好用nvm安装node

clone checkout （**myblog分支**）后

```bash
cd zhangmx.github.io
npm install hexo-cli -g
npm install
```
<!--more-->

创建一篇新博文：

```bash
hexo new "New blog name"
```

去source目录下的_posts找到对应名字的md文件，编写内容。

查看效果：

```bash
hexo s --debug
```

由于采用了[travis-ci](https://travis-ci.org/)部署了自动发布（坑很多），只需要把本分支提交到github就可以了。

打开浏览器，查看效果后，通过ide或者git命令或者git桌面工具直接提交后push改动。

## 编写流程


## 目标

之所以费劲巴拉的这么折腾,就是为了学习git的使用,并理解若干概念,明白什么是什么,和什么该怎么用。涉及的内容：**域名服务管理**、**git操作**、**[MarkDown]()**、**[jekyll]()**、**[jekyllbootstrap]()**、**[gem]()**、**[bundle]()**、**[github-pages](https://pages.github.com/)**、**统计**、**评论**、**主题（[theme](https://hexo.io/themes)）**、**[自动化](https://travis-ci.org/)**。

## 路有点弯
搭建这个环境，

## 简单讲讲遇到的坑



### 有趣（要命）的git
git的提交分为3步，这和svn非常不一样，是这样的：

> git add file_name  
> git commit  
> git push

我用的ide是[jetbrains系](https://www.jetbrains.com/)，git提交的时候有个复选框可以选择在提交的同时，上传（PUSH）。

### SSL安全访问



https

hexo
搭建流程

需要: ssh , nvm , npm , 淘宝镜像




使用流程

异地同步
到新的电脑上部署开发步骤

blog

博客文章设置,参数

categories: Opinion
toc: true


git 常用命令
travis-ci 的坑整理
next 主题修订


### 菜单坑

教程和wiki等文档上说在_config.yml下去掉menu下对应的注释,就会显示对应的菜单,但是没说是根目录下还是主题(theme)目录下的,其实主题目录下的那个_config.yml也起着作用,而且会覆盖掉根目录里面的设置,要么就是取不到跟目录下的设置.



