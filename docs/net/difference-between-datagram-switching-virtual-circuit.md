# 数据报交换&虚电路

的区别

> 原文:[https://www . geeksforgeeks . org/数据报间差异-交换-虚拟电路/](https://www.geeksforgeeks.org/difference-between-datagram-switching-virtual-circuit/)

**1。数据报交换:**
**数据报分组交换**是一种分组交换方法，将每个分组或数据报视为一个独立的实体。每个数据包都是通过自己的网络路由的。这是一种不需要连接的服务。因为连接会话没有特定的通道，所以不需要预留资源。因此，数据包有一个包含所有目的地信息的报头。中间节点评估数据包的报头，并选择适当的链路连接到更靠近目的地的不同节点。

**2。虚拟电路:**
**虚拟分组交换**在源和最终目的地之间建立一条路径，所有分组通过该路径在整个呼叫中被路由的方法被称为虚拟电路交换。因为该连接在用户看来是一个迷恋的物理电路，所以该路径被称为虚拟电路。另一方面，其他通信可能共享同一路径的部分。在数据传输开始之前，源和目的地必须就虚电路路径达成一致。为了做出决定，两个地方之间的所有中间节点都向它们的路由数据库添加一个路由条目。在呼叫建立过程中，还会在源和目的地之间交换附加参数，如最大数据包大小。信息传输完成后，虚电路被清除。

**数据报交换的区别&虚电路交换:**T2】

| **数据报交换** | **虚电路** |
| 它是无连接服务。不需要预留资源，因为连接会话没有专用路径。 | 虚电路是面向连接的，这意味着需要预留资源，如缓冲区、带宽等。在数据传输会话将要使用新设置 VC 的时间内。 |
| 所有数据包都可以自由使用任何可用路径。因此，由于路由器上路由表的动态变化，中间路由器会随时计算路由。 | 第一个发送的数据包会在路径上的每台服务器上预留资源。在连接时间内，后续数据包将遵循与第一个发送数据包相同的路径。 |
| 数据包以随机顺序到达目的地，这意味着它们不需要按照发出的顺序到达。 | 数据包到达目的地的顺序与数据遵循的路径相同。 |
| 每个数据包都可以自由选择任何路径，因此所有数据包都必须与包含源和上层数据信息的报头相关联。 | 所有的数据包都遵循相同的路径，因此只有连接的第一个数据包需要全局报头，而其他数据包不需要。 |
| 数据报网络不如虚拟电路可靠。 | 虚电路非常可靠。 |
| 效率高，延迟更多 | 效率低，延迟少 |
| 但是，实现数据报网络总是容易且经济高效的，因为不需要每次应用程序必须通信时都预留资源并建立专用路径。 | 虚拟电路的实现成本很高，因为每次建立新的连接都必须预留资源，并且在路由器上进行额外的信息处理。 |
| 基于数据报的网络是真正的分组交换网络。传输数据没有固定的路径。 | 虚电路网络为特定的会话使用固定的路径，然后断开连接，必须为下一个会话建立另一条路径。 |
| 广泛应用于互联网 | 用于 X.25，自动柜员机(异步传输模式) |