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

## 介绍

PuTTYAttach主页面
![image](/img/1.png)

### 会话列表


### 菜单和工具栏


### 新建会话对话框


### 设置选项


### 文件传输设置


### XYZModem 文件传输


