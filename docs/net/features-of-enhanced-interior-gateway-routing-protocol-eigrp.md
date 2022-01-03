# 增强型内部网关路由协议(EIGRP)的特性

> 原文:[https://www . geesforgeks . org/features-of-enhanced-internal-gateway-routing-protocol-EIGRP/](https://www.geeksforgeeks.org/features-of-enhanced-interior-gateway-routing-protocol-eigrp/)

增强型内部网关路由协议(EIGRP)是思科专有的混合路由协议，包含距离矢量和链路状态路由协议的功能。这是一个在 88 号协议上工作的网络层协议。

它的一些特点是:

1.  **快速收敛–**EIGRP 使用 DUAL 算法支持快速收敛。如果通往网络的一条路由出现故障，则可以使用另一条路由(可行的后继路由)。如果拓扑表中也没有到该网络的路由，则查询消息被多播以找出到该网络的替代路由。

2.  **带宽使用减少–**EIGRP 不像其他距离矢量路由协议那样定期发送更新。距离矢量路由协议(如 RIP)会在一段时间内发送完整的路由表，因此会不必要地消耗可用带宽，但如果拓扑发生任何变化，EIGRP 会使用部分更新，即仅当发生任何事件时才会触发更新，因此会在需要时消耗带宽。此外，EIGRP 更新只传播给需要的路由器。

3.  **支持所有局域网和广域网数据链路协议和拓扑–**EIGRP 支持 FDDI、令牌环等多址网络，以及租用线路、点对点链路等所有广域网拓扑。EIGRP 不需要任何跨第 2 层协议(如帧中继)的额外配置。

4.  **支持自动总结–**在 EIGRP 中，默认情况下自动总结是启用的。自动总结是一项功能，允许路由协议自动总结到有类网络的路由，即路由器将自动接收总结的路由。EIGRP。例如-1.1.1.1 /24 将自动汇总到有类 1.1.1.1/8

5.  **支持不等成本负载均衡–**通过改变方差的值，可以在 EIGRP 中实现不等成本负载均衡。默认情况下，方差为 1，因此支持等成本负载平衡，但是如果我们想要使用不等成本负载平衡，那么我们可以根据我们想要在不同路径上划分的流量来更改方差的值。可行距离以大于后继者可行距离值的方式相乘。

6.  **通过可靠传输协议(RTP)的通信–**EIGRP 依赖专有协议 RTP 来管理讲 EIGRP 的路由器之间的通信。EIGRP 使用 224.0.0.10 作为其多播地址。对于它发送的每个多播，路由器准备并维护一个路由器列表(说 EIGRP)。如果没有收到多播确认，则通过 16 个单播消息发送相同的数据。如果即使在 16 次单播尝试后仍未收到确认，则它将被宣布死亡。这个过程被称为可靠多播。

7.  **Best path selection using DUAL –** EIGRP uses Diffusing Update Algorithm (DUAL) to find out the best path available to a network. EIGRP speaking routers maintain a topology table in which all the routes to the network are maintained. If the best path (successor) goes down, then the second best path (feasible successor) is used from the topology table. If there is no path available in the topology table then it sends a query message to resolve the query. 

    它主要维护 3 个不同的表:
    **(a)邻居表:**它包含与哪些路由器形成了邻居关系的信息。它包含了 SRTT。它还包含未被确认的 hello 消息的队列计数值。
    **(b)拓扑表:**它包含网络可用的所有路由(可行后继和后继)。
    **(c)路由表:**它包含所有用于做出当前路由决策的路由。此表中的路由被视为后续(最佳路径)路由。

8.  **流量控制–**假设路由器的一个接口连接到 ISP，那么我们不希望该接口成为 EIGRP 过程的一部分。对于这种情况，EIGRP 提供了一种功能，我们可以将接口标记为被动，即不参与 EIGRP 过程。

9.  支持可变长度子网掩码(VLSM)。
10.  支持 IPv4 和 IPv6。