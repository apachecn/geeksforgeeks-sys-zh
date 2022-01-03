# 【HTTP、FTP 和 SMTP 有什么区别？

> 原文:[https://www . geesforgeks . org/http-FTP-和-smtp/](https://www.geeksforgeeks.org/what-are-the-differences-between-http-ftp-and-smtp/) 有什么区别

先决条件–[HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/)、 [FTP](https://www.geeksforgeeks.org/computer-network-file-transfer-protocol-ftp/) 、 [SMTP](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/)
HTTP 代表超文本传输协议，FTP 代表文件传输协议，而 SMTP 代表简单邮件传输协议。这三者都用于通过计算机网络传输信息，是当今互联网不可或缺的一部分。

为什么我们需要三个协议来传输文件？
我们需要这三个协议，因为它们都服务于不同的目的。这些是 HTTP、FTP 和 SMTP。

1.  HTTP 是万维网的主干。它定义了网络浏览器(像火狐、Chrome)和网络服务器通信的消息格式，同时也定义了网络浏览器应该如何响应特定的网络浏览器请求。
2.  顾名思义，FTP 是用于通过通信网络传输文件的底层协议。它建立了两个 TCP 连接:**控制连接**对用户进行身份验证，**数据连接**传输文件。
3.  SMTP 是全球各地的电子邮件服务器用来相互通信的东西，这样您在晚上 11:59 提交的作业就可以在截止日期内到达您教授的收件箱。

它们的实现有何不同？
三者都是[应用层协议](https://www.geeksforgeeks.org/protocols-application-layer/)，使用 TCP 作为底层传输层协议。但是它们的使用方式和实现方式却大不相同。下表简要区分了它们。

<figure class="table">

| 参数 | 超文本传送协议 | 文件传送协议 | 简单邮件传输协议 |
| --- | --- | --- | --- |
| 通道数 | Eighty | 20 和 21 | Twenty-five |
| 频带转移类型 | 带内 | 带外 | 带内 |
| 状态 | 无国籍的 | 保持状态 | – |
| TCP 连接数 | one | 2(数据连接和控制连接) | one |
| TCP 连接的类型 | 可以同时使用持久和非持久 | 持久用于
控制连接。
非持久用于
数据连接 | 坚持的 |
| 协议类型 | 拉协议(主要) | – | 推送协议(主要) |
| 转移类型 | 在网络服务器和网络客户端之间传输文件 | 直接在计算机之间传输 | 通过邮件服务器传输邮件 |

*   HTTP 是无状态的。无状态协议意味着 HTTP 网络服务器不维护哪个请求来自哪个用户。因此，为了给用户提供定制的服务，HTTP 使用了 Cookies。
*   FTP 是带外的，因为它使用单独的通道来发送数据(数据连接)，就像发送控制信息(控制连接)一样。
*   由于 SMTP 比 HTTP 旧得多，它将其所有消息限制为 7 位 ASCII 格式。而 HTTP 没有这样的限制。
*   HTTP 将每个文件封装在不同的 HTTP 消息中。而 SMTP 将邮件的所有内容放在一封邮件中。

</figure>