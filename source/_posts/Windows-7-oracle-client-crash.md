---
title: Windows 7 oracle client crash
toc: true
date: 2016-12-23 10:54:22
tags: [oracle,client]
categories: 数据库
---

win 7 下oracle默认的客户端连接服务器莫名其妙的闪退,秒退,崩溃,反正这几个词在百度都没搜到相应的解决方案.

解决方案: 用管理员方式打开控制台.
<!--more-->

用PL sql连接oracle,登陆后,显示一个空白的提示框,啥啥错误提示都没有.

用oracle官方的client链接,竟然莫名其妙崩溃了,怀疑可能是未安装jdk或者java环境造成的.

但是装完后,崩溃依然.而且找不到相关的日志文件.

明明 tnsnames.ora 配置好了信息,就是连接就崩溃.

后来通过client添加另一个服务器的时候报了一个异常,一搜发现是没有管理员权限.

明明是很简单个事情,竟然折腾这么久
