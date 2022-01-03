# 计算机网络面试常见问题|第 1 集

> 原文:[https://www . geesforgeks . org/common-question-computer-networks-interview-questions-set-1/](https://www.geeksforgeeks.org/commonly-asked-computer-networks-interview-questions-set-1/)

**什么是单播、选播、组播和广播？**
如果消息是从源节点发送到单个目的节点，则称为单播。这通常在网络中完成。

如果消息从源发送到任何给定的目的节点。这在我们希望从任何服务器获取内容的内容交付系统中被大量使用。

如果消息被发送到其他节点的某个子集，则称为多播。用于同一数据有多个接收器的情况。像视频会议一样，在拥有相同数据副本的 CDN 服务器上更新一些东西。
如果消息被发送到网络中的所有节点，则称为广播。这通常用于本地网络，例如 DHCP 和 ARP 使用广播。

**OSI 模型中有哪些层？**
共有 7 层
1。物理层
2。数据链路层
3。网络层
4。传输层
5。会话层
6。表示层
7。应用层

**什么是停止等待协议？**
在停止和等待协议中，发送方在发送帧后等待帧的确认，只有在收到帧的确认时才发送下一帧。

**什么是背驮？**
捎带用于网络层(OSI 模型)的双向数据传输。这个想法是为了提高效率。(接收数据的)捎带确认被挂在(要发送的)数据帧上，而不是发送单独的帧。

**集线器、交换机和路由器的区别？**

| 中心 | 转换 | 路由器 |
| 物理层设备 | 数据链路层设备 | 网络层设备 |
| 简单地向所有端口重复信号 | 不是简单地重复，而是根据媒体访问控制地址或局域网地址过滤内容 | 基于 IP 地址路由数据 |
| 连接单个局域网内的设备 | 可以在一个局域网内连接多个子局域网 | 将多个局域网和广域网连接在一起。 |
| [通过 Hub 连接的所有主机的冲突域](https://en.wikipedia.org/wiki/Collision_domain)保持一个。即任何两个设备发送信号是否会冲突。 | 交换机划分冲突域，但连接设备的[广播域](https://en.wikipedia.org/wiki/Broadcast_domain)保持不变。 | 它划分冲突域和广播域， |
|  |  |  |

详见[网络设备](https://www.geeksforgeeks.org/network-devices-hub-repeater-bridge-switch-router-gateways/)。

**在网页浏览器中输入网址会发生什么？**
一个网址可能包含对 HTML、图像文件或任何其他类型的请求。

1.  如果键入的网址的内容在缓存中并且是新的，则显示该内容。
2.  否则，找到该域的 IP 地址，以便建立 TCP 连接。浏览器进行域名系统查找。
3.  浏览器需要知道一个网址的 IP 地址，以便建立一个 TCP 连接。这就是浏览器需要 DNS 服务的原因。浏览器首先在浏览器缓存中查找 URL-IP 映射，然后在操作系统缓存中查找。如果所有缓存都是空的，那么它会递归查询本地 DNS 服务器。本地域名系统服务器提供 IP 地址。
4.  浏览器使用三次握手建立 TCP 连接。
5.  浏览器发送一个 HTTP 请求。
6.  服务器有一个像 Apache 这样的网络服务器，运行 IIS 来处理传入的 HTTP 请求并发送 HTTP 响应。
7.  浏览器接收 HTTP 响应并呈现内容。

**什么是 DHCP，它是如何工作的？**

1.  DHCP(动态主机配置协议)的思想是使设备无需任何手动配置就能获得 IP 地址。
2.  该设备发送广播消息说“我是新来的”
3.  DHCP 服务器会看到该消息并对设备做出响应，通常会分配一个 IP 地址。网络上的所有其他设备都忽略新设备的消息，因为它们不是 DHCP 服务器。

在无线网络中，接入点通常充当 DHCP 服务器。

**什么是 ARP，它是如何工作的？**
ARP 代表地址解析协议。ARP 用于从网络地址中查找局域网地址。节点通常有目的地 IP 来发送数据包，节点需要链路层地址来通过本地链路发送帧。ARP 协议在这里有所帮助。

1.  该节点向所有节点发送广播消息，告知该 IP 地址的媒体访问控制地址是什么。
2.  具有所提供的 IP 地址的节点用 MAC 地址进行回复。

与 DHCP 一样，ARP 是一种发现协议，但与 DHCP 不同的是，这里没有服务器。

练习[网络测验](https://www.geeksforgeeks.org/quiz-corner-gq/)

你可能也喜欢

*   [常见面试难题](https://www.geeksforgeeks.org/category/puzzles/)
*   [亚马逊最常问的面试问题](https://www.geeksforgeeks.org/amazon-interview-questions/)
*   [微软最常问的面试问题](https://www.geeksforgeeks.org/microsofts-asked-interview-questions/ "Permanent link to Microsoft’s most asked interview questions")
*   [埃森哲最常问的面试问题](https://www.geeksforgeeks.org/accentures-most-asked-technical-interview-questions/ "Permanent link to Accenture’s most asked Interview Questions")
*   [常见的面向对象面试问题](https://www.geeksforgeeks.org/commonly-asked-oop-interview-questions/ "Permanent link to Commonly Asked OOP Interview Questions | Set 1")
*   [常见的 C++面试问题，](https://www.geeksforgeeks.org/commonly-asked-c-interview-questions-set-1/ "Permanent link to Commonly Asked C++ Interview Questions | Set 1")
*   [常见 C 编程面试问题|第一套](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/ "Permanent link to Commonly Asked C Programming Interview Questions | Set 1")
*   [常见 C 编程面试问题|第二集](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/ "Permanent link to Commonly Asked C Programming Interview Questions | Set 2")
*   【DBMS 面试常见问题|第 1 集
*   [常见操作系统面试问题|第 1 集](https://www.geeksforgeeks.org/commonly-asked-operating-systems-interview-questions-set-1/)
*   [常见数据结构面试问题](https://www.geeksforgeeks.org/commonly-asked-data-structure-interview-questions-set-1/ "Permanent link to Commonly Asked Data Structure Interview Questions | Set 1")
*   [常见算法面试问题](https://www.geeksforgeeks.org/commonly-asked-algorithm-interview-questions-set-1/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论