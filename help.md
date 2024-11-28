[English](/help-en.md)

# PuTTYAttach 帮助文档

## 一、主页面

PuTTYAttach初始主页面如下
![image](img/1.png)

(1) 菜单栏

(2) 工具栏

(3) PuTTY会话列表

(4) 连接的PuTTY终端

(5) 状态栏，显示PuTTY会话的简要配置。

### 1.1 工具栏

![image](img/2.png)

**(1) 同步会话**

同步PuTTY的会话到PuTTYAttach。

PuTTY是一个外部独立的程序，可直接管理其自身会话(一般保存在./sessions目录或注册表中)。

这可能会出现PuTTYAttach保存的会话与PuTTY自身会话不同步，"同步会话"功能会把PuTTY的会话同步到PuTTYAttach。

**(2) 新建会话**

新建一个PuTTYAttach会话，同时在PuTTY中创建此会话。

**(3) 新建组**

在会话列表新建一个文件夹，对会话分组管理。

**(4) 删除**

删除PuTTYAttach会话或会话组(文件夹)。

(5) 连接

连接会话列表中选中的会话，或连接下拉菜单中的会话。

**(6) 断开**

断开当前标签的已连接终端。

(7) 首选项

PuTTYAttach的主要配置项。

**(8) 传输选项**

lrzsz外部程序的相关配置。

**(9) 文件下载**

XModem，YModem，ZModem 协议文件下载。需要与[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)和lrzsz协同实现。

**(10) 文件上传**

XModem，YModem，ZModem 协议文件上传。需要与[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)和lrzsz协同实现。

**(11) 关于**

PuTTYAttach 关于对话框。

### 1.2 菜单栏

菜单栏与工具栏基本一致，除了下面两个菜单。

![image](img/3.png)

(1) PuTTYAttach 页面布局设置

- 隐藏或显示"会话列表"; 

- 隐藏或显示"工具栏";

- 隐藏或显示"菜单栏"。



(2) 外部工具

常用的工具软件或快捷方式复制到 ./exTools 目录，PuTTYAttach 将其添加到此菜单中，以快捷打开对应的软件。

### 1.3 会话列表

主页面左侧是会话列表，列出保存在 ./session.json 文件中的PuTTYAttach会话。如下图所示，创建文件夹可以分组管理会话。

![image](img/4.png)

双击会话 - 连接会话

右键双击 - 修改会话配置，

中键双击 - 复制会话创建新会话

### 1.4 多标签

(1) 在标签头右击可弹出PuTTY的系统菜单。

![image](img/5.png)



(2) 拖放文件到终端窗口弹出文件上传菜单。(注:需要[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)协同)

![image](img/6.png)



## 二、首选项

![image](img/7.png)

所有参数保存在./setting.json文件中。

(1) PuTTY程序文件的路径；相对路径也是有效的。

(2) PuTTY会话文件保存的目录。

[PuTTY for win32 storing configuration into file (kotrla.net)](https://jakub.kotrla.net/putty/) 会将PuTTY(原始版本)保存在注册表的会话转存到文件，这里设置这些文件的目录。默认是putty.exe所在目录下中的sessions目录。

(3) 等待putty.exe 启动时间。

启动时间超时。PuTTYAttach启动putty.exe超时，认为putty.exe启动失败。

(4) PuTTYAttach退出时保存

1) 程序布局 :  显示/隐藏 (会话列表，工具栏，菜单栏)。

2) 已打开的会话 : PuTTYAttach退出时，没有关闭的会话。

(5) 同时删除PuTTY会话

PuTTYAttach创建会话的参数保存在./session.json 文件，PuTTY自身的会话参数保存在 (2) 选项的目录中。

删除会话时首先删除./session.json 文件中的会话参数，勾选此项会启动putty.exe删除PuTTY自身保存的会话参数。

(6) 国际化

PuTTYAttach默认语言是中文，目前完成了英文翻译(./translations/english.qm)。

【注】

english.qm 是通过Google翻译的，准确性可能不是那么高。发现翻译不对可自行修改english.qm。

其他语言可以使用QT Creator的工具翻译工具创建新的xxx.qm文件，复制到./translations目录，可在"Language"中看到并选择。

## 三、新建会话

![image](img/8.png)

**(1) 会话名称**

这是一个重要的参数，./session.json 文件的会话参数与PuTTY自身会话参数通过会话名称关联。

输入会话名称后将同步发送到PuTTY程序的会话名称输入框中，PuTTY以此名称保存自身会话参数。

**(2) 别名**

终端标签的标签头默认显示会话名。

设置别名并勾选，标签头显示别名。

**(3) 线路延迟**

通信线路的时延。身份验证发送用户名，密码之间的发送间隔，命令序列两条命令之间的发送间隔，由此参数决定。

**(4) 命令<CR>/<LF>转换**

命令默认是以回车<CR>结尾的，选择<CR><LF>项,命令将以<CR><LF>结尾，发送给远端。

**(5) 连接后发送<CR>**

一些服务器(如串口通信)，身份验证使用提示方式是无法自动触发的。

连接后发送<CR>触发"自动身份验证"和"自动发送命令序列"。

**(6) 身份验证**

勾选此项，终端连接后，依次发送用户名，密码验证身份，登录远端服务器。

这里输入的密码会简单加密保存在./session.json文件中，加密强度不高，如有严格的安全要求不要使用此功能。

**(7) 发送命令序列**

勾选此项，执行自动身份验证后，依顺序发送序列里的命令。

**(8) 连接时运行脚本**

登录脚本。勾选此项，执行自动身份验证后，运行此脚本。

此功能V1.0版还不支持，计划往后的版本中实现。

**(9) PuTTY程序配置界面**

PuTTY自身会话的参数配置，与PuTTY单独使用时一致。

**(10) 文件传输**

会话有关文件传输的参数，包括XModem，YModem，ZModem。

文件传输需要[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)和lrzsz协同实现。

### 3.1 自动身份验证

自动身份验证有两种方式: 提示方式，延时方式。

#### 3.1.1**提示方式**

用户名提示 -- 远端服务器发送的输入用户名的提示字符。如 "login as:"。

密码提示 -- 远端服务器发送的输入密码提示字符。如 "password:"。

终端连接后等待远端服务器发来用户名提示后发送用户名，等待远端发来密码提示后发送密码，完成身份登录验证。

【注】

需要与[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)协同实现。

PuTTYAttach会一直等待提示字符，某些情况下可能会一直等待不往下执行**"自动发送命令序列"**。退出等待的方法是连续两次"**回车键**"。

#### 3.1.2**延时方式**

"用户名提示" 和 "密码提示" 置空。

终端连接后发送用户名，等待2倍线路延迟，发送密码完成身份登录验证。

【注】

PuTTYAttach通过模拟键盘按键方式发送密码到PuTTY，因为命令行方式传递密码会直接泄露。

### 3.2 自动发送命令序列

**"Add按钮"** 新增一行

**"Delete按钮"** 删除选中行

**"Up按钮"** 向上移动选中行

**"Down按钮"** 向下移动选中行

**"Expect列"**  等待命令期待的字符串，然后发送命令。

**"Send列"** 具体命令

"Expect列" 为空，以延时方式按顺序发送命令。

"Expect列" 不为空，需要与[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)协同实现。

命令序列同样通过模拟键盘按键方式发送到PuTTY。

【注】

PuTTYAttach会一直等待"Expect列"的期待字符串，退出等待的方法是连续两次"**回车键**"。

退出等待后，整个"自动发送命令序列"任务将退出，不再发送后续命令。



下图是**自动身份验证**和**自动发送命令序列**的配置和实际例子:

![image](img/s1.png)

### 3.3 登录脚本

此功能V1.0版还不支持，计划往后的版本中实现，需要与[pipPuTTY](https://github.com/hfcjx/pipPuTTYcn)协同实现。

### 3.4 XYZModem

![image](img/9.png)



#### 3.4.1 参数配置

**(1) 文件上传设置**

**"lsz.exe命令行"**  

启动lsz.exe时的命令行参数，参数的意义通过命令 "lsz --help" 查看。

**“上传文件发送远端命令”** 

勾选此项，PuTTYAttach 启动XYZModem文件上传，会发送此命令到远端服务器启动XYZModem文件接收，自动完成文件传输。



**(2) 文件下载设置**

**"lrz.exe命令行"**  

启动lrz.exe时的命令行参数，参数的意义通过命令 "lrz --help" 查看。

**“下载文件发送远端命令”** 

勾选此项，PuTTYAttach 启动XYZModem文件下载，发送此命令到远端服务器启动XYZModem文件发送，自动完成文件传输。



**(3) XYModem分组大小**

只对XModem，YModem有效。文件上传数据分组大小分别是128字节或1024字节。



**(4) 自动激活**

勾选此项，PuTTYAttach监控终端输入的命令。

输入命令与**“上传文件发送远端命令”**和**“下载文件发送远端命令”**匹配(全部命令选项,顺序不限)；

**“上传文件发送远端命令”**和**“下载文件发送远端命令”**是空，输入命令与lrzsz默认命令项: **"--xmodem"**或**"--ymodem"**匹配。

如输入命令匹配成功，启动本地lrzsz自动完成文件传输。

【注】 

Zmodem协议匹配的是协议帧头，不依赖**“上传文件发送远端命令”**或**“下载文件发送远端命令”**。

#### 3.4.2 自动文件传输

##### **3.4.2.1 远端发起**

终端输入lrzsz命令启动远端文件传输，然后在PuTTYAttach启动本地lrzsz，称为远端发起文件传输。

勾选**自动激活**，终端输入lrzsz命令后，PuTTYAttach匹配命令成功自动启动本地lrzsz，自动完成文件传输。

###### 1  **文件上传**

(1) 终端中输入**"rz --ymodem -E"**命令，启动远端YModem文件接收。

(2) PuTTYAttach弹出**"选择上传文件窗口"**，选取要上传的文件。

(3) 弹出**文件上传与下载窗口**自动完成文件发送。

如下图

![image](img/s2.png)

###### 2 **文件下载**

终端中输入**"sz --ymodem -k ui.xml log.txt"**命令，启动远端YModem文件发送。

PuTTYAttach弹出**"文件上传与下载窗口"**，自动完成文件接收。

如下图

![image](img/s3.png)



##### **3.4.2.2 本地发起 **

PuTTYAttach启动本地lrzsz，自动发送lrzsz命令启动远端文件传输，称为本地发起文件传输。

勾选**“上传文件发送远端命令”**和**“下载文件发送远端命令”**，PuTTYAttach自动发送命令到远端，自动完成文件传输。

###### 1 **文件上传**

(1) PuTTYAttach 菜单启动**ZModem上传**

(2) PuTTYAttach弹出**"选择上传文件窗口"**，选取要上传的文件。

(3) PuTTYAttach自动发送**“上传文件发送远端命令”**的命令到远端。

(4) 弹出**文件上传与下载窗口**自动完成文件发送。

![image](img/s4.png)



【注】 XModem协议无法传输文件名，弹出**"输入远端保存文件名窗口"**输入远端保存的文件名，文件名自动附加在**“上传文件发送远端命令”**命令后面，发送到远端。

![image](img/10.png)

###### 2 **文件下载**

(1) PuTTYAttach 菜单启动**XModem下载**

(2) PuTTYAttach弹出**"输入远端发送文件窗口"**，填写要下载的文件。PuTTYAttach会把文件名自动附加在**“下载文件发送远端命令”**最后发送到远端。

(3) PuTTYAttach弹出**"XModem本地保存文件窗口"**，输入文件本地保存的文件名(YModem和ZModem没有此步)。

(4) 弹出**文件上传与下载窗口**自动完成文件接收。

(5) 下载文件保存目录里成功接收并保存为"a.txt"。

![image](img/s5.png)





## 四、文件传输lrzsz设置

![image](img/11.png)

所有参数保存在./setting.json文件中。

(1) 下载文件默认保存目录。

(2) lrz.exe的路径。

(3) lsz.exe的路径。

(4) 每次下载文件都选择保存文件的路径。

(5) 下载文件时遇到重名文件，自动重命名。对应lrz.exe的命令行参数是"-E"。

## 五、文件上传与下载窗口

![image](img/12.png)

(1) 传输过程信息。

(2) 异常或事件信息。

(3) 下载完成后打开下载文件保存目录。

(4) 窗口关闭后，lrzsz冗余信息保存到文件，文件是 lrzsz所在目录下的"PuttyAttach_lrzszLog.txt"。

## 【附录】

**(1)  原始PuTTY与pipPuTTY区别：**

pipPuTTY实现了与外部程序传入和传出数据，以此扩展:

1) 提示字符方式的身份认证和命令发送
2) 文件上传和下载。

| 功能                         | 原始PuTTY | pipPuTTY |
| ---------------------------- | --------- | -------- |
| 会话管理                     | ●         | ●        |
| 多标签                       | ●         | ●        |
| 自动身份认证(提示方式)       |           | ●        |
| 自动身份认证(延时方式)       | ●         | ●        |
| 自动发送命令序列(Expect方式) |           | ●        |
| 自动发送命令序列(延时方式)   | ●         | ●        |
| 脚本                         |           | ●        |
| 文件传输(XYZModem)           |           | ●        |



**(2）[lrzsz-win32](https://github.com/trzsz/lrzsz-win32)和[lrzsz-pip](https://github.com/hfcjx/lrzsz)区别**

lrzsz-win32是原始版本lrzsz的win32编译版本。

[lrzsz-win32](https://github.com/trzsz/lrzsz-win32)和[lrzsz-pip](https://github.com/hfcjx/lrzsz) 与 PuTTYAttach协同都可以实现文件的上传和下载。

[lrzsz-pip](https://github.com/hfcjx/lrzsz) 在原始lrzsz基础上对齐XModem，YModem，ZModem传输过程中打印的冗余信息，文件上传下载窗口展示的传输过程信息更详细。



**(3) PuTTYAttach 发布**

[hfcjx/PuTTYAttach: PuTTYAttach是一个基于Windows的应用程序，用于管理PuTTY会话，多标签显示；支持自动登录](https://github.com/hfcjx/PuTTYAttach)



