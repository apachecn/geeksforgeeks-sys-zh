# 计算机网络|第 5 集

> 原文:[https://www.geeksforgeeks.org/computer-networks-set-5/](https://www.geeksforgeeks.org/computer-networks-set-5/)

GATE CS 2005 考试提出了以下问题。

**1)同一会话的数据包可以通过不同的路径路由到:**T2(a)TCP，但不是 UDP
(b) TCP 和 UDP
(c) UDP，但不是 TCP
(d)既不是 TCP 也不是 UDP

回答(b)
数据包是网络层[协议数据单元(PDU)](http://en.wikipedia.org/wiki/Protocol_data_unit) 。TCP 和 UDP 是传输层协议。相同会话的数据包可以通过不同的路由进行路由。大多数网络不使用静态路由，而是使用某种形式的自适应路由，其中用于为同一会话路由两个数据包的路径可能因某些链路上的拥塞或其他原因而不同。

**2)地址解析协议(ARP)用于:**
(a)从 DNS 中查找 IP 地址
(b)查找默认网关的 IP 地址
(c)查找与 MAC 地址对应的 IP 地址
(d)查找与 IP 地址对应的 MAC 地址

答案(d)
[地址解析协议(ARP)](http://en.wikipedia.org/wiki/Address_Resolution_Protocol) 是一种用于从 IP 地址中查找 MAC 地址的请求和回复协议。

**3)使用 n 位帧序列号的选择性拒绝协议进行数据传输的最大窗口大小为:**
(a)2^n
(b)2^(n-1)
(c)2^n–1
(d)2^(n-2)

回答(b)
在[选择性拒绝(或选择性重复)](http://en.wikipedia.org/wiki/Selective_Repeat_ARQ)中，窗口的最大尺寸必须是最大序列号的一半。

**4)在由网桥连接的局域网网络中，数据包通过中间网桥从一个局域网发送到另一个局域网。由于两个局域网之间可能存在多条路径，数据包可能必须通过多个网桥路由。为什么生成树算法用于网桥路由？**
(a)用于局域网之间的最短路径路由
(b)用于避免路由路径中的环路
(c)用于容错
(d)用于最小化冲突

回答(b)
使用生成树的主要思想是避免循环。详见[生成树协议](http://en.wikipedia.org/wiki/Spanning_Tree_Protocol)。

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论