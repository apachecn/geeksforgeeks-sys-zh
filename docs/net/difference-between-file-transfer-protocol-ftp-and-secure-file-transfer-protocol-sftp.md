# 文件传输协议(FTP)和安全文件传输协议(SFTP)的区别

> 原文:[https://www . geesforgeks . org/文件传输协议差异-ftp 和安全文件传输协议-sftp/](https://www.geeksforgeeks.org/difference-between-file-transfer-protocol-ftp-and-secure-file-transfer-protocol-sftp/)

FTP 代表[文件传输协议](https://www.geeksforgeeks.org/computer-network-file-transfer-protocol-ftp/)。这是一种用于将文件从一台主机传输或复制到另一台主机的协议。但是在不同的主机或系统中发送和接收文件时，可能会出现不同的文件名和不同的文件目录等问题。而在 FTP 中，不提供安全通道在主机或系统之间传输文件。它用于 21 号港口。

SFTP 代表**安全文件传输协议**。这是一种提供安全通道的协议，用于将文件从一台主机传输或复制到另一台主机或系统。SFTP 在 SSH 协议下建立控制连接，用于 22 号端口。

它们之间有一些区别，如下所示:

<figure class="table">

| S.NO | 文件传送协议 | science for the people 为人类服务的科学 |
| --- | --- | --- |
| 1. | 它代表文件传输协议。 | 它代表安全文件传输协议。 |
| 2. | 在 FTP 中，不提供安全通道在主机之间传输文件。 | 在 SFTP，提供安全通道在主机之间传输文件。 |
| 3. | 它是 TCP/IP 协议的一部分。 | 它是一个 SSH 协议。 |
| 4. | 它通常在 21 号港口运行。 | 它在 22 号港口运行。 |
| 5. | 它在 TCP 协议下建立连接。 | 它在 SSH 协议下建立控制连接。 |
| 6. | 它不会在发送前加密数据。 | 它在发送前加密了数据。 |
| 7. | 它适用于文件传输的直接方法。 | 它使用隧道方法传输文件。 |
| 8. | 它使得上传和下载文件没有任何安全性。 | 它通过使用 SSH 密钥来维护数据的完全安全性。 |
| 9. | 它使用两个通道。 | 一边；SFTP 只使用一个频道。 |
| 10. | 它不需要任何验证。 | 在 SFTP，用户需要使用用户名和密码或 SSH 密钥对 FTP 客户端进行身份验证。 |
| 11. | FTP 更快。 | 它比 FTP 慢。 |

</figure>