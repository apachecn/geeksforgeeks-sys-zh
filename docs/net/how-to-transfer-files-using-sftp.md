# 如何使用 SFTP 传输文件？

> 原文:[https://www . geeksforgeeks . org/如何使用-sftp/](https://www.geeksforgeeks.org/how-to-transfer-files-using-sftp/) 传输文件

**SFTP(安全文件传输协议)**或 SSH(安全外壳)文件传输协议)是一种用于在客户端和服务器之间传输文件的文件传输协议。它使用 [SSH(安全套接字层)](https://www.geeksforgeeks.org/introduction-to-sshsecure-shell-keys/)，也称为安全套接字层文件传输协议。它为安全传输文件提供了对远程服务器的安全访问。

安全 FTP 的出现是为了满足隧道技术增强安全性的需要。它使用安全外壳 2 (SSH2)来创建安全隧道，并模拟 FTP 连接，以提供一个防火墙友好的加密通道来使用流行的 TCP 端口 22 传输文件。SSH 通过使整个文件传输会话(包括所有会话控制命令)始终完全加密来提供增强的安全性，同时只需要在防火墙上打开一个端口，而不是需要为 FTP 和 SSL 连接打开两个端口。

SFTP 使用 SSH 协议传输文件。您需要首先配置 SSH。检查您是否配置了 SSH。在您的服务器上执行以下操作

```
$ ssh geeksforgeeks@your_server_ip_or_remote_hostname.
```

用您的用户名替换**“geeks forgeeks”**，用您的服务器 ip 或主机名替换**“您的服务器 IP 或远程主机名”**。

如果成功并且你登录了。你可以走了。如果没有，您需要首先设置 SSH 访问。

然后退出提示符。

```
$ exit
```

**建立 SFTP 会话:**
我们可以使用以下命令连接到 SFTP 会话。

```
$ sftp geeksforgeeks@your_server_ip_or_remote_hostname
```

此命令会将您连接到远程会话，并且提示符会变为 SFTP 提示符。

如果您使用的是自定义 SSH 端口(不是默认端口 22)，那么您可以使用以下命令连接到 SFTP。

```
$ sftp -oPort=customport geeksforgeeks@your_server_ip_or_remote_hostname.
```

在这里，将**“custom port”**更改为您正在使用的端口号。此命令将使用您指定的端口将您连接到 SFTP。

**与 SFTP 传输文件:**

**1。将远程文件传输到本地系统–**
如果我们想从远程主机传输文件，可以使用以下命令。

```
sftp> get remote-file
```

```
Output
Fetching home/geeksforgeeks/remote-file to remote-file
/home/geeksforgeeks/remote-file                       100%   40KB  39.8KB/s   00:05
```

在这里，远程文件将是您想要传输的文件的名称。get 命令将在本地系统上下载**“remote file”**，其名称与服务器上的名称相同。

我们可以通过在远程文件名后指定名称，用不同的远程主机将**远程文件**下载到我们的机器上。

```
sftp> get remote-file local-file
```

get 命令也可以将一些标志作为选项。例如，如果我们想要复制一个目录及其所有内容，我们可以使用**-r”**递归标志。

```
sftp> get -r some-directory
```

**2。将本地文件传输到远程系统–**
使用 **put** 命令可以轻松地将文件从本地系统传输到远程系统。

```
sftp> put localFile
```

```
Output
Uploading local-file to /home/geeksforgeeks/local-file
local-file                                     100% 7607     7.4KB/s   00:00
```

**放**可以用的选项旗和**拿**可以用的一样。所以，要复制一个完整的目录就要它的所有文件你都可以用。

```
sftp> put -r local-directory
```

**结论:**
SFTP 是利用 FTP 或 SCP 的力量在本地和远程文件和文件夹之间执行传输的较好方式。