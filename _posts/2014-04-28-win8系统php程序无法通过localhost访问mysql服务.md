---
layout: post
title: win8系统php程序无法通过localhost访问mysql服务
keywords: php,访问mysql,win8.1
description: win8系统php程序无法通过localhost访问mysql服务
tags: [ win8,ipv6 ]
---

刚装了win8,使用了下挺好用的,然后配置了下web环境,安装过程也一切顺利,没有出现什么错误.
结果完了之后运行了下以前的程序发现链接不了数据库了.

mysql服务起来了,端口也没有被占用,防火墙也通过了,但是php程序就是不能访问,诡异的是通过命令行可以连接,
本以为是hosts的问题,结果检查了下也没问题.

到最后ping了下localhost发现,返回的不是127.0.0.1,而是::1.

原来是win8.1默认开了ipv6,这就好办了,关掉之后访问正常了.

如何彻底关掉ipv6,仅仅在以太网属性中取消是不够的.
	
	打开注册表：HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\TCPIP6\Parameters
	新建 DWORD(32位) 项，
	名称:DisabledComponents
	值:FF
	保存，重启后IPV6完全禁用，ipconfig也看不到相关的信息了！
