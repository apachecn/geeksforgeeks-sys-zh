# TCP 连接终止

> 原文:[https://www.geeksforgeeks.org/tcp-connection-termination/](https://www.geeksforgeeks.org/tcp-connection-termination/)

在 [TCP 三次握手过程](https://www.geeksforgeeks.org/computer-network-tcp-3-way-handshake-process/)中，我们研究了如何使用 **SYN** 位段在传输控制协议(TCP)中建立客户端和服务器之间的连接。在本文中，我们将研究 TCP 如何密切客户端和服务器之间的连接。这里，我们还需要将位段发送到服务器，该服务器的 **FIN** 位被设置为 1。

与大多数面向连接的传输协议一样，TCP 支持两种类型的连接释放:

1.  **Graceful connection release –** 
    In the Graceful connection release, the connection is open until both parties have closed their sides of the connection. 
2.  **突然连接释放–**
    在突然连接释放中，要么一个 TCP 实体被迫关闭连接，要么一个用户关闭数据传输的两个方向。

**突然连接释放:**
发送 RST 段时进行突然连接释放。出于以下原因，可以发送 RST 段:

1.  当接收到不存在的 TCP 连接的非同步段时。

2.  在开放连接中，当收到报头无效的数据段时，一些 TCP 实现会发送 RST 数据段。这将通过关闭相应的连接来防止攻击。

3.  当某些实现需要关闭现有的 TCP 连接时，它们会发送一个 RST 段。他们将关闭现有的 TCP 连接，原因如下:
    *   缺乏支持连接的资源

    *   远程主机现在无法访问，并且已停止响应。

当一个 TCP 实体发送一个 RST 段时，如果它不属于任何现有的连接，它应该包含 00，否则它应该包含该连接的序列号的当前值，并且确认号应该被设置为该连接上的下一个预期的序列内序列号。

**优雅连接释放:**
终止 TCP 连接的常见方式是使用 TCP 报头的 FIN 标志。这种机制允许每台主机单独释放自己的连接端。

![11](img/4e8bf311d0d2367c8e43a698dff1931a.png)

机制如何在 TCP 中工作:

1.  **步骤 1(来自客户端的 FIN)–**
    假设客户端应用程序决定要关闭连接。(请注意，服务器也可以选择关闭连接)。这使得客户端向服务器发送一个 **FIN** 位设置为 **1** 的 TCP 段，并进入 **FIN_WAIT_1** 状态。当处于 **FIN_WAIT_1** 状态时，客户端等待来自服务器的带有确认(ACK)的 TCP 段。
2.  **步骤 2(来自服务器的确认)–**
    当服务器从发送方(客户端)接收到 FIN 位段时，服务器立即向发送方(客户端)发送确认(确认)段。
3.  **步骤 3(客户端等待)–**
    当处于 **FIN_WAIT_1** 状态时，客户端等待来自服务器的带有确认的 TCP 段。客户端收到该段后，进入 **FIN_WAIT_2** 状态。当处于 **FIN_WAIT_2** 状态时，客户端等待来自服务器的另一个段，其中 FIN 位设置为 1。
4.  **步骤 4(来自服务器的 FIN)–**
    在服务器发送 ACK 段一段时间后(因为服务器中的一些关闭过程)，服务器向发送方(客户端)发送 FIN 位段。
5.  **步骤 5(来自客户端的确认)–**
    当客户端从服务器接收到 FIN 位段时，客户端确认服务器的段并进入 **TIME_WAIT** 状态。**时间 _ 等待**状态允许客户端重新发送最终确认，以防**确认**丢失。客户端处于 **TIME_WAIT** 状态的时间取决于它们的实现，但是它们的典型值是 30 秒、1 分钟和 2 分钟。等待之后，连接正式关闭，客户端的所有资源(包括端口号和缓冲区数据)都被释放。

下图说明了服务器端和客户端访问的一系列状态，假设客户端开始连接拆除。在这两个状态转换图中，我们只显示了 TCP 连接是如何正常建立和关闭的。

客户端访问的 TCP 状态–

![](img/93325a4e0105fb40c6bef4fe70ad57c0.png)

服务器端访问的 TCP 状态–

![](img/19358ff153509d90f177908e39d82609.png)

在这里，我们没有描述在某些场景中会发生什么，比如当连接的两端都想同时启动或关闭时。如果你有兴趣了解更多关于这个和其他关于 TCP 的高级问题，鼓励你看史蒂文斯的综合书籍。

**GATE 问题–**
考虑一个 TCP 客户端和一个 TCP 服务器运行在两台不同的机器上。完成数据传输后，TCP 客户端调用**关闭**终止连接，并向 TCP 服务器发送一个 FIN 段。服务器端 TCP 通过发送一个确认来响应，该确认由客户端 TCP 接收。根据 TCP 连接状态图(RFC 793)，客户端 TCP 连接在什么状态下等待服务器端 TCP 的 FIN？
(A)最后确认
(B)时间等待
(C)飞行等待-1
(D)飞行等待-2

**解说:** (D)
[GATE CS 2017(第 1 集)，第 12 题](https://www.geeksforgeeks.org/gate-gate-cs-2017-set-1-question-12/)

**参考资料–**
[TCP 连接终止–维基百科](https://en.wikipedia.org/wiki/Transmission_Control_Protocol#Connection_termination)
[http://www . Bau . edu . jo/user portal/user profile/poststatch/10617 _ 1870 _ 1 . pdf](http://www.bau.edu.jo/UserPortal/UserProfile/PostsAttach/10617_1870_1.pdf)

本文由 [**卡丹·帕特尔**](https://auth.geeksforgeeks.org/profile.php?user=kd) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。