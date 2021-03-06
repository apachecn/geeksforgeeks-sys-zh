# 虚电路和数据报网络的区别

> 原文:[https://www . geesforgeks . org/虚电路和数据报网络之间的差异/](https://www.geeksforgeeks.org/differences-between-virtual-circuits-and-datagram-networks/)

提供面向连接服务的计算机网络称为虚拟电路，而提供无连接服务的网络称为数据报网络。就现有知识而言，我们使用的互联网实际上是基于网络级别的数据报网络(无连接)，因为从源到目的地的所有数据包都不遵循相同的路径。
让我们在这里看看这两个热门辩论话题的突出区别是什么:

**虚电路:**

1.  它是面向连接的，这意味着有一个像缓冲区，中央处理器，带宽等资源的保留。新设置的虚电路将被数据传输会话使用的时间。
2.  第一个发送的数据包会在路径上的每台服务器上预留资源。在连接时间内，后续数据包将遵循与第一个发送数据包相同的路径。
3.  由于所有数据包都将遵循相同的路径，因此需要一个全局报头。只有连接的第一个数据包需要全局头，其余数据包一般不需要全局头。
4.  由于所有数据包都遵循特定的路径，因此数据包会在目的地按顺序接收。
5.  虚拟电路交换确保所有数据包成功到达目的地。由于资源不可用，不会丢弃任何数据包。
6.  从以上几点可以得出结论，虚拟电路是一种高度可靠的数据传输方法。
7.  虚电路的问题是，每次建立新连接时，必须在路径上的每台路由器上保留资源和额外信息，如果许多客户端试图同时保留路由器的资源，这就会成为问题。
8.  它由自动柜员机(异步传输模式)网络使用，专门用于电话呼叫。

**数据报网络:**

1.  这是一种无连接服务。不需要预留资源，因为连接会话没有专用路径。
2.  所有数据包都可以自由使用任何可用路径。因此，由于路由器上路由表的动态变化，中间路由器会随时计算路由。
3.  由于每个数据包都可以自由选择任何路径，因此所有数据包都必须与一个报头相关联，该报头包含有关源和上层数据的正确信息。
4.  无连接属性使数据包以任何顺序到达目的地，这意味着它们可能会在接收端被无序接收。
5.  数据报网络不如虚拟电路可靠。
6.  数据报包交换的主要缺点是，只有当缓冲区、中央处理器和带宽等资源可用时，包才能被转发。否则，数据包将被丢弃。
7.  但是，实现数据报网络总是容易且经济高效的，因为在每次应用程序必须通信时，保留资源并建立专用网络不会带来额外的麻烦。
8.  它通常由 IP 网络使用，该网络用于像互联网这样的数据服务。

本文由**维舍什巴派**供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息