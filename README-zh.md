# PuTTYAttach

PuTTYAttach是一个基于Windows的应用程序，用于多标签管理PuTTY终端。

支持自动登录,登录脚本，支持XModem，YModem，ZModem协议传输文件。

## 背景

一个量产很久的设备包含一个简单的串口终端，包含YModem协议支持上传和下载文件，一直使用免费版XShell交互很完美。

近期需要让其支持TCP连接的远程终端，XShell的支持就不那么好了，需要找其他终端工具替代。

找了好几个终端工具，发现PuTTY是最合适的一个，支持串口，TCP-RAW，命令交互很完美，美中不足的是PuTTY原生不支持YModem协议，会话管理不是很便捷。

在github找到一个工具superPuTTY: https://github.com/jimradford/superputty . 可以管理PuTTY会话。

在研究YModem协议时，找到开源工具 lrzsz: https://github.com/trzsz/lrzsz-win32 . 支持XModem，YModem，ZModem，很多Linux SSH连接也支持此工具。

是否可以开发一个软件，把superPuTTY 和 lrzsz 糅合在一起，满足设备交互的终端工具？于是有了PuTTYAttach。

## 特点

1.多标签管理PuTTY终端 ，

2.管理PuTTY会话，支持分组和层次组合。

3.连接后自动身份认证。

4.登录后自动发送命令序列。

5.集成外部工具。

6.Python脚本支持(V1.0版本不支持，计划以面版本实现)。

7.整合lrzsz，支持XModem，YModem，ZModem协议下载和上传文件。

注: 

1-5 是PuTTYAttach 基础功能，适配原始的PuTTY终端和变种的PuTTY终端。

6-7 是扩展功能，需要与pipPuTTY配合使用。

pipPuTTYcn https://github.com/hfcjx/pipPuTTYcn

pipPuTTYen https://github.com/hfcjx/pipPuTTYen

## 介绍

PuTTYAttach初始主页面如下
![image](/img/1.png)

(1) 菜单栏

(2) 工具栏

(3) PuTTY会话列表

(4) 连接的PuTTY终端

(5) 状态栏，显示PuTTY会话的简要配置。

### 工具栏

![image](/img/2.png)

(1) 同步会话

    同步PuTTY的会话到PuTTYAttach。

    PuTTY是一个外部独立的程序，可直接管理其会话。可能与PuTTYAttach中的会话不再同步，此时可用"同步会话"功能把PuTTY的会话同步到PuTTYAttach。

(2) 新建会话

    新建一个PuTTYAttach会话，同时在PuTTY中创建此会话。

(3) 新建组

    在会话列表新建一个文件夹，对会话分组管理。

(4) 删除

    删除PuTTYAttach会话或会话组(文件夹)。

(5) 连接

    连接会话列表中选中的会话，或连接下拉菜单中的会话。

(6) 断开

    断开当前标签的已连接终端。

(7) 首选项

    PuTTYAttach的主要配置项。

(8) 传输选项

    lrzsz外部程序的相关配置。

(9) 文件下载

    XModem，YModem，ZModem 协议文件下载。

(10) 文件上传

    XModem，YModem，ZModem 协议文件上传。

(11) 关于

    PuTTYAttach 关于对话框。

### 菜单栏

菜单栏与工具栏基本一致，除了下面两个菜单。

![image](/img/3.png)

(1) PuTTYAttach 页面布局设置

    隐藏或显示"会话列表"; 隐藏或显示"工具栏"; 隐藏或显示"菜单栏"。

(2) 罗列外部工具

    把你常用的工具软件或其快捷方式复制到 ./exTools 目录，PuTTYAttach 为你将其添加到此菜单中，可快捷地打开对应的软件。

### 会话列表

主页面左侧是会话列表，罗列PuTTYAttach的所有会话，会话保存在 ./session.json 文件中。

![image](/img/4.png)

如上图所示，创建文件夹可分组管理会话。

双击会话将连接会话，右键双击修改会话配置。

### 多标签

![image](/img/5.png)

在标签头右击可弹出PuTTY的系统菜单。

### 首选项


### 新建会话


### 自动身份认证


### 自动发送命令序列


### 文件传输设置


### XYZModem 文件传输


