# 各种 TCP 和 UDP 端口

> 原文:[https://www.geeksforgeeks.org/various-tcp-and-udp-ports/](https://www.geeksforgeeks.org/various-tcp-and-udp-ports/)

传输层约定利用端口和多路复用/多路分解的思想，将信息传递给监听网络节点的各个服务。这些端口由一个单独的 16 位数字表示，这意味着它们可以构成 0-65535 的数字范围。这个范围被 IANA(互联网号码分配机构)分成几个不同的部分:

*   端口 0 不用于互联网/网络流量，但有时用于同一台计算机上不同程序之间的通信。
*   端口 1-1023 被称为系统端口。这些端口是最著名的系统管理和许多常见网络服务的官方端口。HTTP 通常在端口 80 通信，而 FTP 在端口 21。在大多数工作框架/操作系统中，管理级别的访问需要启动一个在系统端口上调谐的程序。
*   端口 1024-49151 被称为注册端口。这些端口用于一系列不同的网络功能和服务，这些功能和服务可能不会像系统端口那样经常使用。注册端口的真实情况是 3306，它是众多数据库可以调谐的端口。在某些情况下，注册港口得到 IANA 的正式登记和承认，但这并不一定总是如此。在大多数操作系统上，任何入门级别的任何客户端都可以在注册端口上运行程序调优。
*   最后，从端口 49152-65535 有一系列端口。这些端口被称为临时端口(或专用端口)。短暂端口不能在 IANA 注册，通常用于设置出站网络流量和连接。所有的 TCP 流量都需要一个目的端口和一个源端口来建立连接。当客户端需要与服务器通话时，客户端将被指定一个临时端口，仅用于该连接，而服务器则接入静态系统框架或注册端口。

不是每一个运行的操作系统都遵循 IANA 短暂的港口提议。用于出站关联的临时端口包括端口 49152 到 65535。然而，这个范围的端口可以根据您正在处理的操作系统和框架而变化。注册端口被使用了很多次，但是，没有一个现代操作系统会将系统端口用于出站连接。

以下是一些常用的端口供参考:

<figure class="table">

| 港口 | 服务 | 描述 | 传输协议 |
| --- | --- | --- | --- |
| seven | 回声 | 端口只是回显发送给它的任何内容。此功能可用于许多攻击，如 Smurf/Fraggle。 | TCP 和 UDP |
| 20 /21 | 文件传输协议 | FTP 协议用于向客户端发送数据的端口 | 传输控制协议（Transmission Control Protocol） |
| Twenty-two | 安全外壳 | 用作远程登录的安全替换协议 | TCP 和 UDP |
| Twenty-three | 用于远程联接服务的标准协议或者实现此协议的软件(可为动词) | 远程登录用于远程连接到工作站或服务器的端口(不安全) | 传输控制协议（Transmission Control Protocol） |
| Twenty-five | 简单邮件传输协议 | 用于通过互联网发送电子邮件 | 传输控制协议（Transmission Control Protocol） |
| Fifty-three | 域名系统 | 用于 DNS 请求、网络路由和区域传输的端口 | TCP 和 UDP |
| 67 /68 | 动态主机配置协议 | 用于不使用静态 IP 地址分配的网络。 | 用户数据报协议(User Datagram Protocol) |
| Eighty | 超文本传输协议 | 用于在浏览器上浏览网页 | 传输控制协议（Transmission Control Protocol） |
| One hundred and ten | 邮局协议(POP3) | 用于检索服务器邮箱完整内容的端口 | 传输控制协议（Transmission Control Protocol） |
| One hundred and forty-three | 互联网消息访问协议 | 互联网消息访问协议(IMAP4)是一种新的协议，以更广泛的操作阅读电子邮件 | TCP 和 UDP |
| One hundred and ninety-four | 互联网中继聊天协议 | 允许多方之间以文本形式进行通信，一个或多个客户端可以连接到中央服务器。 | TCP 和 UDP |
| Four hundred and forty-three | 带安全套接字层的 HTTP | 用于安全网络流量的端口 | TCP 和 UDP |
| Three thousand three hundred and eighty-nine | 远程桌面协议(RDP) | 远程桌面用来远程管理其他 windows 系统的端口 | TCP 和 UDP |

传输层有许多端口，可以同时容纳许多不同的应用协议。端口由传输层连接的类型决定。
此外，请记住，应用层有很多协议，但并非所有协议都需要端口号(如 TCP 或 UDP)。互联网控制消息协议就是其中之一。

要更加熟悉端口，并查看指定给不同服务的端口列表，请查看 [IANA 服务名称和传输协议端口号注册表](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)。在[维基百科](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)上有一份可比较的端口和相应服务的列表，这是一个相当简短和容易阅读的列表。也看看吧！。

</figure>