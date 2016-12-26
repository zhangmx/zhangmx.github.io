---
title: Create ELK
toc: true
date: 2016-12-19 11:08:52
tags: [elk,elasticSearch,logstash,kibana]
categories: 运维
---
在统计分析项目里的D服务器就是由elk组成的,主要负责收集日志,和分析结果.

之所以把这个文字归到运维里,是因为后来才发现,这东西其实很多公司都是用来统计运维相关的日志的,里面提供了很多相关的分析模板.
<!--more-->

搭建ELK其实很简单的,看官网文档,和很多博客都有写.

我用了最简单的方式,没有采用编译的方式安装.主要学习了[ELKstack 中文指南](https://www.gitbook.com/book/chenryn/elk-stack-guide-cn/details)

### 下载好对应的包后,执行安装:

``` bash
sudo yum localinstall elasticsearch-5.0.2.rpm
sudo yum localinstall kibana-5.0.2-x86_64.rpm
sudo yum localinstall logstash-5.0.2.rpm
```
删除:

``` bash
sudo yum remove elasticsearch
sudo yum remove logstash
sudo yum remove kibana
```

### 如果使用 x-pack
``` bash
cd /usr/share/elasticsearch
sudo bin/elasticsearch-plugin install file:///path/to/x-pack-5.0.2.zip
```
删除:
``` bash
# 删除后，需要修改对应的原来用到过密码的配置文件
sudo bin/elasticsearch-plugin remove x-pack
```

``` bash
cd /usr/share/kibana
sudo bin/kibana-plugin install file:///path/to/x-pack-5.0.2.zip
```
删除:
``` bash
sudo bin/kibana-plugin remove x-pack
```

最好准备两套配置文件,一套带密码的,一套不带;x-pack是收费的,可以搞一个免费的license,但是过期后,所有权限将失效,也就是任何人只要能访问到kibana的页面不需要登陆就能操作,这是一个销售小哥通过邮件告知我的.

当然,可以通过ip地址约束这个页面,也可以通过其他方式.

### 相关操作

``` bash
sudo systemctl restart logstash
sudo systemctl start logstash
sudo systemctl stop logstash
sudo systemctl status logstash

sudo systemctl restart kibana.service
sudo systemctl start kibana.service
sudo systemctl stop kibana.service
sudo systemctl status kibana.service

sudo systemctl restart elasticsearch
sudo systemctl start elasticsearch
sudo systemctl stop elasticsearch
sudo systemctl status elasticsearch


```
也可以用 service,不过centos 7 之后,最小化安装后,好多命令都没有,连ifconfig这样的命令都没有了[可以看看这个](https://dougvitale.wordpress.com/2011/12/21/deprecated-linux-networking-commands-and-their-replacements/)
``` bash
sudo service elasticsearch status
```

Deprecated command  | Replacement command(s)
------------- | -------------
arp | 	ip n (ip neighbor)
ifconfig | 	ip a (ip addr), ip link, ip -s (ip -stats)
iptunnel | 	ip tunnel
iwconfig | 	iw
nameif | 	ip link, ifrename
netstat | 	ss, ip route (for netstat-r), ip -s link (for netstat -i), ip maddr (for netstat-g)
route | 	ip r (ip route)

