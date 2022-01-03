# 管理距离(AD)和自治系统(AS)

> 原文:[https://www . geesforgeks . org/administration-distance-ad-and-autonomous-system-as/](https://www.geeksforgeeks.org/administrative-distance-ad-and-autonomous-system-as/)

**管理距离(AD)** 用于评估从邻居路由器接收的路由信息的可信度。AD 最少的路由将被选为到达目的远程网络的最佳路由，该路由将被放在路由表中。它定义了路由协议的可靠性。它是一个介于 0 到 255 之间的整数值，其中 0 表示该路由最受信任，255 表示不会有流量通过该路由，或者该路由从未安装在路由表中。

<figure class="table">

| 路由来源 | 默认广告 |
| 连接接口 | Zero |
| 静态路由 | one |
| 外部 BGP | Twenty |
| 加强型内部网关路由协议 | Ninety |
| 开放式最短路径优先(Open Shortest Path First Interior Gateway Protocol) | One hundred and ten |
| 长裂口 | One hundred and twenty |
| 外部 EIGRP | One hundred and seventy |
| 内部 BGP | Two hundred |
| 未知的 | 255(不使用此路线) |

*   **Example –** 
    The smaller the value of AD, the more reliable the routing protocol is. For example, if a router receives an advertised route to a remote destination network from OSPF and EIGRP, then the advertised route of EIGRP will be considered as the best route and will be placed in the routing table as EIGRP has lower AD. 
*   **动态协议的最佳路径选择过程–**
    如果路由器从远程网络的多个源接收到相同的通告路由，则检查第一个 AD 值。广告值最小的广告路由将获得优先权。如果通告路由的广告值相同，则检查通告路由的度量。度量最小的通告路由将被放在路由表中。如果广告和度量相同，则负载平衡完成，即流量将通过不同的路由。负载平衡可以相等也可以不相等。在相等的负载平衡中，相同数量的流量将一次通过两条路由，而不同数量的流量将在不相等的负载平衡中通过。

**自治系统(AS)** 是在单个管理域下工作的一组路由器和网络。它是定义路由器路由域的 16 位值。这些数字的范围从 1 到 65535。

*   **公共自治系统号–**
    这些是 16 位值，范围从 1 到 64511。如果客户连接到多个互联网服务提供商，如多宿主，服务提供商将提供公共服务协议。当客户希望通过两个互联网服务提供商传播其 BGP 路由时，会提供一个唯一的全球自治号码。

*   **专用自治系统号–**
    专用自治系统号是 16 位值，范围从 64512 到 65535。当客户希望多连接到单个 ISP(单个家庭或双家庭网络)而不是多个 ISP 时，服务提供商将向客户提供专用自治系统号。提供这些是为了保存自治系统编号。

*   **分配自治系统号码–**
    自治系统号码首先由 IANA(互联网号码分配机构)分配给各自的区域注册管理机构。此外，区域登记处将这些自治号码(来自 IANA 提供的自治号码块)分发给其指定区域内的实体。

</figure>