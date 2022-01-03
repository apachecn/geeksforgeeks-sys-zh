# 什么是网络交换机，它是如何工作的？

> 原文:[https://www . geesforgeks . org/什么是网络交换机及其工作原理/](https://www.geeksforgeeks.org/what-is-a-network-switch-and-how-does-it-work/)

交换机是一种网络设备，用于将网络划分为不同的子网，称为子网或局域网网段。它负责根据媒体访问控制地址过滤和转发局域网网段之间的数据包。

*   At [OSI model](https://www.geeksforgeeks.org/layers-of-osi-model/)
*   Work in the data link layer of, and check for errors before forwarding data.
*   Transfer data only to addressed devices.
*   Working in full duplex mode
*   Allocate limited bandwidth for each LAN segment

**工作:**

当源想要将数据包发送到目的地时，数据包首先进入交换机，交换机读取其报头并找到目的地的媒体访问控制地址来识别设备，然后通过通向目的地设备的适当端口将数据包发送出去。

交换机在通信源和目的地之间建立临时连接，并在会话完成后终止连接。此外，它还同时为进出设备的网络流量提供全部带宽，以减少冲突。

交换技术用于决定源和目的地之间数据传输的最佳路由。这些分为三类:

1.  [[circuit switching]](https://www.geeksforgeeks.org/circuit-switching-in-computer-network/)
2.  [[message exchange]](https://www.geeksforgeeks.org/message-switching-techniques/)
3.  [packet switching](https://www.geeksforgeeks.org/packet-switching-and-delays-in-computer-network/)

**优势:**

1.  By dividing the network into smaller subnets, traffic overload in the network is prevented.
2.  Increase network bandwidth.
3.  Reduce frame collisions because the switch creates a collision domain for each connection.

**缺点:**

1.  It cannot prevent traffic destined for different LAN segments from reaching all other LAN segments.