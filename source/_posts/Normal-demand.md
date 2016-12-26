---
title: Normal demand
toc: true
date: 2016-12-24 11:02:55
tags: [node,php,swoole,websocket,Broadcasting]
categories: 需求
---

前天同事提到一个服务器推送行情的需求,然后考虑了一个实现方案,结果昨天一个旧同事也问询了我这个几乎一模一样的需求,感觉这个需要很实际啊

<!--more-->

行情必然是实时的,网页手机端据说都能很好的处理websocket,觉得这个应该可以.

A 行情展示页面
B 推送服务器
C 行情源服务器
D 广播服务器

行情展示页面通过websocket和B推送服务器交换数据,其实就是一个聊天室.D广播服务器作为终端用户的服务器端,同时也是B的客户端.从C服务器中获取内容,然后广播出去.

实现方案设计到的技术: node.io swoole 都可以很容易搭建websocket服务器,也就是B .D采用python的[websocket client](https://github.com/liris/websocket-client),swoole作为服务器端的同时还提供了创建客户端的方法.
