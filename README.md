# PuTTYAttach 简介

PuTTYAttach打包发布，解压即可使用。

## PuTTYAttach是什么

PuTTYAttach是一个Windows的程序，仅适用于 Microsoft（c） Windows（c） 平台。

PuTTYAttach用于组织PuTTY会话和多标签展示PuTTY连接，支持XModem，YModem，ZModem协议收发文件，自动用户密码发送和自动预设命令序列发送。

详细介绍请看 [帮助文档](/help.md)


## 技术特点

- 列表组织会话，支持多层次管理
- 内嵌PuTTY.exe，同一个窗口中新建，修改，保存PuTTY会话。
- 多标签展示连接的会话，标签可显示会话名或别名
- 自动用户名，密码发送，完成自动登录
- 自动发送预设的命令行序列
- *整合lrzsz，支持XModem，YModem，ZModem协议文件传输
- *监控远端服务器lrzsz命令，自动激活本地lrzsz，自动完成文件传输
- *启动本地lrzsz，自动发送lrzsz命令到远端服务器，自动完成文件传输
- *运行脚本

【注】 *需要 [pipPuTTYcn](https://github.com/hfcjx/pipPuTTYcn) 或 [pipPuTTYen](https://github.com/hfcjx/pipPuTTYen) 配合。

## 为什么有PuTTYAttach

有一个设备具有一个简单的串口shell服务器，支持YModem协议上传和下载文件，使用免费版的XShell交互，一直很好地工作。

现在设备需要增加TCP/IP连接，shell服务器同时支持串口和TCP-Raw连接，XShell不支持TCP-Raw，需要另寻其他的Shell工具。

SecureCRT同时支持串口和TCP-Raw连接，Ymodem协议文件传输，很完美的完成交互工作，但是SecureCRT不是免费软件。

PuTTY被称为世界上最好的 telnet / SSH 客户端，同时支持串口和TCP-Raw连接，开源免费，但是原生不支持YModem协议。
无意间发现了XModem，YModem，ZModem协议的开源软件lrzsz，完美的支持YModem协议。

因此就有了一个想法，开发一个桥梁软件把PuTTY和lrzsz整合在一起，完成XModem，YModem，ZModem协议文件传输功能，后来把PuTTY的会话管理和多标签展示也实现了，于是就有了PuTTYAttach。


