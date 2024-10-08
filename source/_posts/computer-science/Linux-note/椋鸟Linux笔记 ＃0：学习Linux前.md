---
title: 椋鸟Linux笔记#0：学习Linux前
date: 2024-05-24 20:55:21
category:
  - [计算机科学, Linux笔记]
tags:
  - Linux
math: true
---

:::info
该系列为本人的学习笔记，主要由本人整理书写而成。部分内容来自教材、视频课程等，不能保证完全原创性。
:::

萌新的学习笔记，写错了恳请斧正。

### 关于Linux

Linux 是一种开源操作系统，其核心由林纳斯·托瓦兹于1991年开发，基于UNIX设计理念。Linux内核本身仅是操作系统的核心部分，负责管理硬件资源，而完整的Linux系统还包括工具和库，这些通常由GNU计划提供。因此，完整的系统经常被称为“GNU/Linux”。

Linux有多种发行版，每种都有自己的软件库和管理工具，例如Ubuntu、Fedora和Debian等。这些发行版适应了从个人桌面计算到服务器，再到嵌入式系统等不同的使用场景。

Linux广泛应用于服务器、超级计算机、网络设备，以及日益增长的移动设备和家庭设备中，特别是其在Android操作系统的核心组成部分中的使用，使其成为世界上应用最广泛的操作系统之一。

### Linux环境的搭建

我们自己搭建Linux环境一般有下面几种方法：

#### 直接安装Linux系统

直接将系统安装到主机上使用，就像我们使用Windows那样。

但是这样非常不方便（哪怕是安装为双系统或者多系统），而且后面网络编程时不利于体验通信。

#### 安装在虚拟机上

本地使用VMware、VirtualBox等虚拟机软件，将Linux系统安装到虚拟机中。
这样使用较为方便，但是虚拟机网络需配置为桥接，也不利于后面网络编程。

#### 安装为WSL2子系统

利用Windows11提供的新特性，部署WSL2后直接在MSStore中安装相应版本的Linux系统。
这样使用非常方便，但是缺点和虚拟机类似。

#### 使用云服务

在云服务提供商（阿里云、百度云、腾讯云等处购买云服务器，然后本地通过XShell等软件或者直接控制台ssh链接到服务器即可。从云服务提供商处获得的云服务器一般是自带公网IPv4点，这是我们自己难以做到的。

优点是非常方便使用和管理，而且利于后面网络部分的学习。缺点是价格一般较高（哪怕学生第一年的超优惠价格也是99块1年）（但是可以白嫖）。

+++primary 白嫖云服务（不是广告）

:::info
下面的白嫖方法应当是有时效性的活动，请注意本内容写于2024年5月21日。
:::

阿里云有为学生提供免费的云服务，能白领7个月的Linux服务器，活动网页如下：

{% links %}
- site: 阿里云学生权益
  url: https://developer.aliyun.com/plan/student
  color: "#39c5bb"
{% endlinks %}

这个只要认证学生身份就能领一个月，完成Clouder认证就能续领6个月（非常简单跟着提示做就行）。

+++

购买完云服务后我们应该做的是：

1. 在云服务商的控制台查看我们服务器的公网IP地址，保存或者记下来。
2. 设置root用户的密码。

### 直接控制台连接远程服务器

我们打开电脑的控制台，直接连接服务器我们可以输入：

```bash
ssh root@114.114.114.114
# 注意这里root是指管理员账户，后面是服务器的公网IP地址
```

随后按照提示输入密码即可。

或者我们只输入公网IP，随后根据提示输入用户名和密码：

```bash
ssh 114.114.114.114
# 后面是服务器的公网IP地址
```

### 使用XShell连接远程服务器

使用像XShell这样的软件连接，功能更多更强大，可以方便以后的操作。

XShell的下载官网是：

{% links %}
- site: Xshell
  url: https://www.xshell.com/zh/xshell/
  color: "#39c5bb"
{% endlinks %}

使用XShell的话需要注意一些点：

1. XShell下允许使用复制和粘贴快捷键，复制是`Ctrl`+`Insert`，粘贴是`Shift`+`Insert`。
2. 要解决连接后出现警告`The remote SSH server rejected X11 forwarding request.`我们只需要执行代码`yum install xorg-x11-xauth`即可。
