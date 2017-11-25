---
layout: post
title: "redis 入门"
date: 2017-11-25 11:09:04 PM 
comments: true
---
#### 1、[win下安装](https://jingyan.baidu.com/article/0f5fb099045b056d8334ea97.html)   
	修改密码：redis.windows-service.conf文件中，去掉requirepass前的注释“#” 后边加上自己的密码

#### 2、常用服务命令  
    在安装路径redis下   
    卸载服务：redis-server --service-uninstall

	开启服务：redis-server --service-start

	停止服务：redis-server --service-stop

#### 3、密码验证
    启动服务以后： auth 自己的密码

#### 4、[命令参考 redis中文](http://www.redis.cn/commands.html) 、  [博客园](http://www.cnblogs.com/mxh1099/p/5626149.html)

   