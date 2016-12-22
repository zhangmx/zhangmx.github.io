---
title: New to Asp dot net
toc: true
date: 2016-12-19 11:02:22
tags:  [asp,net,deploy]
categories: language
---
2007年学习的时候,接触了一点asp的内容,部门新接手了一个asp.net的站点,于是简单研究了一下.

在感叹廉颇老矣的同时,默默的对各种环境下的web编程做了一个错略的对比.

不得不说,虽然内心有过对windows系的鄙视,但是整体体验上还是很棒的.VS世界上最好的开发工具!

.net程序员做开发的时候,主要的任务就是找到各种操作的按钮在哪就够了(真的花了我好多时间).

<!--more-->

一个新的2008服务器上遇到的坑如下:

1,默认的2008并没有 .net framework4.0.3923,但站点设置中却有这个设置,而在程序跑起来的时候,会提示"无法识别的特性 targetFramework
2,安装完framework4.5后,在两个4.5目录下执行 aspnet_regiis -i –enable
3,提示当前站点用户没有 Framework64\v4.0.30319\Temporary ASP.NET Files 的写访问权限,需要设置一下这个文件夹对站点用户的权限.
4,[部署工具](https://www.iis.net/downloads/microsoft/web-deploy) 下载, [url rewrite](https://www.iis.net/downloads/microsoft/url-rewrite)下载.


项目并没有引用其他额外的库,[nuget](https://www.nuget.org/)没用上.

据说[saltstack](https://docs.saltstack.com/en/latest/)做部署比较好,尚未研究.
