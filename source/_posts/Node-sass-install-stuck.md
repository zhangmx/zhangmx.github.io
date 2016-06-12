---
title: Node sass install stuck
toc: true
date: 2016-06-12 08:02:25
categories: Nodejs
---
#node-sass install

之前用vagrant的homestead创建laravel项目后，执行`npm install`都很顺利，但是昨天遇到一个奇怪的问题，安装一半后，卡在了sass安装命令上，等了有一两个小时，不超时，不中断，也没有错误日志。

这个在之前其他项目都是好好的，所以感觉问题应该出在网络上，或者由于node已经有了新版本，版本交叉兼容的问题。

但是看sass的官方页面说支持node 5，于是反复重新安装了几次，依然卡在install命令的位置。

github上有个[issue](https://github.com/sass/node-sass/issues/1568)应该是一样的问题。

另外有几个node6的支持的问题，说用`npm rebuild node-sass`在尝试无果后，看到几个提示一些工具需要安装为全局模式。执行安装全局模式后，提示没有权限。然后就用sudo安装了一下，感觉会不会是权限问题导致sass卡住。结果用`sudo npm install`安装成功。

以上操作都是在虚拟机homestead里完成的，所以如果是独立的机器，也许会没有这个问题，特别是虚拟机还是vagrant的情况。

