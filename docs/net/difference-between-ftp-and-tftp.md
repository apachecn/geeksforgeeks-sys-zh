# FTP 和 TFTP 的区别

> 原文:[https://www . geesforgeks . org/FTP 和-tftp 的区别/](https://www.geeksforgeeks.org/difference-between-ftp-and-tftp/)

[**FTP**](https://www.geeksforgeeks.org/computer-network-file-transfer-protocol-ftp/)**:**
FTP 代表文件传输协议。这种协议用于将文件从一台主机传输或复制到另一台主机。但是在不同的主机或系统中发送和接收文件时，可能会出现不同的文件名和不同的文件目录等问题。而在 FTP 中，不提供安全通道在主机或系统之间传输文件。FTP 在两个端口上工作:20 和 21 一个用于数据，另一个用于连接控制。

[**【TFTP】**](https://practice.geeksforgeeks.org/problems/what-is-the-difference-between-tftp-and-ftp-application-layer-protocols)**:**
TFTP 代表琐碎文件传输协议。TFTP 用于将文件从客户端传输到服务器或从服务器传输到客户端，而不需要 FTP 功能。TFTP 的软件比 FTP 小。TFTP 在 69 端口号上工作，其服务由 UDP 提供。

现在，我们将看到 FTP 和 TFTP 的区别:

<figure class="table">

| S.NO | 文件传送协议 | 普通文件传送协议(Trivial File Transfer Protocol) |
| 1. | 代表文件传输协议。 | TFTP 代表普通文件传输协议。 |
| 2. | FTP 的软件比 TFTP 大。 | 而 TFTP 的软件比 FTP 小。 |
| 3. | FTP 在两个端口上工作:20 和 21。 | 而 TFTP 在 69 号港口工作。 |
| 4. | FTP 服务由 TCP 提供。 | 而 TFTP 服务则由 UDP 提供。 |
| 5. | FTP 的复杂度比 TFTP 高。 | 而 TFTP 的复杂度比 FTP 复杂度低。 |
| 6. | FTP 中有很多命令或消息。 | TFTP 只有 5 条信息。 |
| 7. | FTP 通信需要认证。 | 而 TFTP 通信不需要认证。 |
| 8. | FTP 通常适合远程用户上传和下载文件。 | 而 TFTP 主要用于网络设备之间的配置传输。 |
| 9. | FTP 是一种可靠的传输协议。 | 一边；TFTP 是一个不可靠的传输协议。 |
| 10. | FTP 是基于 TCP 的。 | 一边；TFTP 是基于 UDP 的。 |
| 11. | FTP 比较慢。 | 与文件传输协议相比，TFTP 的速度更快。 |

</figure>