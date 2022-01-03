# GRE 全模

> 原文:[https://www.geeksforgeeks.org/gre-fullform/](https://www.geeksforgeeks.org/gre-fullform/)

**GRE** 或**通用路由封装**是思科开发的隧道协议。它将 IP 数据包(即可传送的内部数据包)封装到外部数据包中。它将它们传输到一个设备，该设备将它们解封装，并通过网络将其路由到最终目的地。

**特点:**

*   GRE is a routing encapsulation protocol.
*   GRE provides a stateless, private connection.
*   GRE protocol creates a point-to-point connection similar to virtual private network (VPN).
*   Adopt logical hub-and-spoke topology.
*   It can carry any OSI Layer 3 protocol on an IP network.
*   GRE provides communication between two hosts in different private networks by establishing a tunnel between two routers on the Internet.
*   GRE connection endpoints can be terminated with the help of virtual tunnel interface (VTI) existing in each device.

**优势:**

*   GRE protocol supports encapsulation of IPv4 broadcast multicast traffic. It also supports IPv6.
*   GRE is a simple and flexible protocol.
*   GRE tunnel encapsulates multiple protocols under one protocol.
*   GRE can also route non-TCP/IP protocols such as IPX or AppleTalk through IP networks.
*   GRE protocol can connect multiple discontinuous subnets.
*   GRE protocol allows you to set up a virtual private network (VPN) over a wide area network (WAN).
*   GRE protocol can also easily work in networks with limited hop count.
*   GRE protocol is easy to debug.

**缺点:**

*   GRE protocol does not provide data encryption facilities, that is, network security cannot be guaranteed. It needs to be integrated with other secure tunnel protocols such as IPSec to provide network security.
*   GRE protocol has poor scalability because defining GRE tunnel is a manual task.