---
title: Vagrant and docker
toc: true
date: 2016-12-22 09:33:05
tags: [vagrant,docker]
categories: 运维
---

vagrant和docker都研究了一下,下面做一个简单的对比.
<!--more-->

假如把vagrant和docker整合一下,就是vagrant打包出一个含有docker的box,一定是疯了,不过我之前就是这么想的

vagrant把一个部署好了的 virtualbox(或VMware) 里的环境打包成box文件

docker把调整好的环境打包成image,并且有一个类似版本库一样的迭代管理方式

vagrant和docker类似,但是比docker重,毕竟每启动一个vagrant,就是新开一个虚拟机,而docker相当于新开了一个软件而已,虽然虚拟机也可以看做软件,但是资源占用是不同的.

vagrant是从laravel的文档里提到的homestead的了解到这个东西的,刚接触的时候感觉这个东西真的很方便.

homestead对vagrant做了一些封装,还提供了几个alias,比如 homestead up == vagrant up

但是我觉得这样搞完全没有必要,而且反而增加了学习负担,而且对熟练vagrant是一个小小的障碍,因此推荐使用vagrant的时候,用不着搞那些封装.

不过话说回来,homestead对vagrant的配置文件进行了一个抽离,把独立的各个功能分块,并把常用的配置放在一个yaml文件里,这样的确方便了一点点.

可是话虽如此,个人觉得还是用vagrant默认的配置就很好,而且足够用了.
