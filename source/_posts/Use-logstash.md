---
title: Use logstash
toc: true
date: 2016-11-16 10:57:11
tags: [logstash]
categories: logstash
---

# 使用logstash


logstash的[官方文档](https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html)和[中文文档](http://kibana.logstash.es/content/logstash/)中有遗漏的地方,在官方论坛里也提到文档的更新比较滞后,主要遇到的问题:


使用包管理工具安装后,程序被安装在了/usr/share目录下,并没有在/usr/local下面,因此直接执行logstash会提示找不到这个命令.

文档中提到的命令行测试安装是否成功的命令在最新的5.0几版本中需要额外的一个参数`--path.settings=/etc/logstash`,这个参数制定的是配置文件所在的目录.

因此那个测试命令应该是介样婶的

``` bash
sudo /usr/share/logstash/bin/logstash --path.settings=/etc/logstash -e 'input { stdin { } } output { stdout {} }'
```
或者(json输出)
``` bash
sudo /usr/share/logstash/bin/logstash --path.settings=/etc/logstash -e 'input { stdin { } } output { stdout {codec=>rubydebug} }'
```

但是还需要在配置目录下创建一个空的文件

``` bash
sudo touch /etc/logstash/conf.d/empty.conf
```

官方论坛上说以后的发行包里会加上一个默认的这个文件,所以在未来的版本中查看一下这个目录下如果有了现成的conf而不是空的情况就不必执行这个命令.

展示图:

![命令执行情况](images/logstash.png)


如果报错了,可以去`/var/log/logstash/logstash-plain.log`这个文件中看一眼什么地方出错了.

PS:这个破程序启动很慢,不知道是虚拟器配置低的问题,还是ruby活着java程序就是介样慢

PPS:退出命令行的输入模式需要用ctrl+D

