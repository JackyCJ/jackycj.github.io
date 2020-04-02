---
layout:     post
title:      macOS 开启 VNC 远程桌面和 SSH 服务
subtitle:   macOS 开启 VNC 远程桌面和 SSH 服务
date:       2019-10-10
author:     
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - MacOS
    - SSH
    - VNC

---

# macOS 开启 VNC 远程桌面和 SSH 服务

准备用 macOS 来做为服务器，既然是服务器，那不可缺少的是远程管理，实际上 macOS 自带 VNC 远程桌面和 SSH 服务，只是默认没有开启，下面我们来开启它们。

## 一、开启 VNC

macOS 开启 VNC 服务可以实现远程桌面控制，方法是：系统偏好设置 -> 共享，打开屏幕共享，添加相应的账号就可以了，如下图：

![](https://tva1.sinaimg.cn/large/006y8mN6gy1g7yysgfe3wj31140titlx.jpg)

客户端那边如果也是 macOS，就在浏览器输入 IP 地址，比如：vnc://192.168.4.92，就会打开屏幕共享的客户端，输入用户名密码就可以连接成功，如下图：

![](https://tva1.sinaimg.cn/large/006y8mN6gy1g7yyvzw7xtj31110u0qv6.jpg)


## 二、开启 SSH 服务

macOS 默认是有 SSH 客户端，但是默认没有开 SSH 服务，打开的方法是：系统偏好设置 -> 共享，打开远程登录就，然后添加相应的账户可以了，如下图：
![](https://tva1.sinaimg.cn/large/006y8mN6gy1g7yywu5wixj31140tigxd.jpg)

转载自[https://www.exchen.net/macos-开启-vnc-远程桌面和-ssh-服务.html](https://www.exchen.net/macos-开启-vnc-远程桌面和-ssh-服务.html)
