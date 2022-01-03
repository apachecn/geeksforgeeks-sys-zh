# 应用层协议

> 原文:[https://www.geeksforgeeks.org/protocols-application-layer/](https://www.geeksforgeeks.org/protocols-application-layer/)

### 应用层:-

应用层位于现场视察模型的顶部。它是用户交互的层。它为用户提供服务。

### 应用层协议:-

#### 1.TELNET:

Telnet 代表 **TEL** 词根 **NET** 作品。它有助于终端仿真。它允许远程登录客户端访问远程登录服务器的资源。它用于管理互联网上的文件。它用于交换机等设备的初始设置。telnet 命令是使用 Telnet 协议与远程设备或系统通信的命令。telnet 的端口号是 23。

**命令**

```
telnet [\\RemoteServer]
\\RemoteServer   : Specifies the name of the server to which you want to connect
```

#### 2.文件传输协议:

FTP 代表文件传输协议。它是真正让我们传输文件的协议。它可以在任何两台使用它的机器之间促进这一点。但是 FTP 不仅仅是一个协议，它还是一个程序。FTP 通过可靠高效的数据传输，促进通过远程计算机共享文件。文件传输协议的端口号是数据 20，控制 21。

**命令**

```
ftp machinename
```

#### 3.TFTP:

普通文件传输协议(TFTP)是 FTP 的精简版，但如果你确切知道你想要什么和在哪里找到它，它是首选协议。这是一种在网络设备之间传输文件的技术，是 FTP 的简化版本。TFTP 的港口号码是 69。

**命令**

```
tftp [ options... ] [host [port]] [-c command] 
```

#### 4.NFS:

它代表网络文件系统。它允许远程主机通过网络装载文件系统，并与这些文件系统交互，就像它们在本地装载一样。这使系统管理员能够将资源整合到网络上的集中式服务器上。NFS 的港口号码是 2049。

**命令**

```
service nfs start
```

#### 5.SMTP:

它代表简单邮件传输协议。它是 TCP/IP 协议的一部分。SMTP 使用一种称为“存储和转发”的过程，在网络上移动您的电子邮件。它与邮件传输代理(MTA)密切合作，将您的通信发送到正确的计算机和电子邮件收件箱。SMTP 的端口号是 25。

**命令**

```
MAIL FROM:<mail@abc.com?
```

#### 6.LPD:

它代表行打印机守护程序。它是为打印机共享而设计的。它是接收和处理请求的部分。“守护进程”是服务器或代理。LPD 的港口号码是 515。

**命令**

```
lpd [ -d ] [ -l ] [ -D DebugOutputFile]
```

#### 7.x 窗口:

它为基于图形用户界面的客户机/服务器应用程序的编写定义了一个协议。这个想法是允许一个名为客户端的程序在一台计算机上运行。它主要用于互连的大型机网络。X 窗口的端口号从 6000 开始，每台服务器增加 1。

**命令**

```
Run xdm in runlevel 5 
```

#### 8.简单网络管理协议:

它代表简单网络管理协议。它通过以固定或随机的时间间隔从管理站轮询网络上的设备来收集数据，要求它们披露某些信息。这是服务器共享当前状态信息的一种方式，也是管理员修改预定义值的一种途径。SNMP 的端口号是 161(TCP)和 162(UDP)。

**命令**

```
snmpget -mALL -v1 -cpublic snmp_agent_Ip_address sysName.0
```

#### 9.域名系统:

它代表域名系统。因此，每次使用域名时，域名系统服务都必须将该名称转换为相应的 IP 地址。例如，域名 www.abc.com 可能翻译成 198.105.232.4。
DNS 的端口号为 53。

**命令**

```
ipconfig /flushdns
```

#### 10.DHCP:

它代表动态主机配置协议。它给主机提供 IP 地址。当主机向 DHCP 服务器注册 IP 地址时，DHCP 服务器可以向主机提供许多信息。DHCP 的端口号是 67，68。

**命令**

```
clear ip dhcp binding {address | * }
```

本文由**克里特卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。