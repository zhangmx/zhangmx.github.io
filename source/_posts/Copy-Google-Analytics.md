---
title: Copy Google Analytics
toc: true
date: 2016-12-19 11:07:42
tags: [google,analytics,javascript]
categories: javascript
---
公司有个类似baidu或者google统计的那种需求.于是简单研究了一下,最后选用了google做研究.

被采集用户行为页面所在服务器(A)
采集用户行为信息的服务器(B)
统计脚本所在服务器(C)
分析统计结果服务器(D)

<!--more-->

反混淆的[ga代码](https://gist.github.com/zhangmx/0927215b4cb4dc3ee1d8ddc81af2a3a3)

网上有好多研究这种统计分析的博客或者帖子,但是大多没有完整代码,囫囵半片的

仔细学习了[使用nginx lua实现网站统计中的数据收集](https://www.centos.bz/2013/09/nginx-lua-website-analysis-collection/),[使用ELK(Elasticsearch + Logstash + Kibana) 搭建日志集中分析平台实践](https://wsgzao.github.io/post/elk/index.html)

这里有个坑,elk分析系统的logstash如果读取日志文件的格式是自定义的,需要自己编辑一份解析的配置文件.而用linux下的隐藏字符 ctrl v ctrl A,如教程提到的方式,除了增加维护者的负担,也增加了logstash的负担.

logstash会把解析好的内容打包成json,然后发给elasticSearch,而如果日志格式原本就是json,就少了一层处理,而且无论是从维护性上,还是性能上都是个不错的方式.


另外两片内容中有一些过时了的东西,这种事情真是很难维护,毕竟,谁会没事闲的看自己以前写的东西还对不对呢,如果可以像wiki那样开放修改,又没人能确保修改是无误的.

毕竟连官网的帮助文档都跟不上版本发布的步骤.

还有:

https://developers.google.com/analytics/devguides/collection/analyticsjs/command-queue-reference#method-details


openresty相关:

http://jinnianshilongnian.iteye.com/category/333854

https://github.com/openresty/nginx-tutorials


