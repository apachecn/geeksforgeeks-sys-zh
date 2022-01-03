# 【OSPF 和 IS-IS 的区别

> 原文:[https://www . geesforgeks . org/OSPF 和 is-is 之间的区别/](https://www.geeksforgeeks.org/difference-between-ospf-and-is-is/)

**1。 [OSPF](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-protocol-states/) :**
它的开发是因为互联网社会的需求，为 [TCP/IP 协议](https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/)社区推出一个高功能的非专有 IGP。

OSPF 是一种域内路由协议，基于链路状态路由技术。它引入了一些新概念，如路由更新认证、可变长度子网掩码(VLSM)、根总结等。

**2。信息系统-信息系统:**
中间系统到中间系统是一种标准化的链路状态协议，被开发为[现场视察模型](https://www.geeksforgeeks.org/osi-model-full-form-in-computer-networking/)的最终路由协议。

IS-IS 是链路状态 IGP。链路状态协议通过在每台参与路由器上构建完整网络连接图所需的信息循环来区分。这张地图然后被用来计算到达目的地的最短路径。

主要用于互联网服务提供商环境。

**OSPF 和 IS-IS 的区别:**

<center>

| 没有。 | 参数 | 开放式最短路径优先(Open Shortest Path First Interior Gateway Protocol) | 是-是 |
| 1. | 管理距离 | One hundred and ten | One hundred and fifteen |
| 2. | 标准 | RFC 2328 （OSPFv2）. | ISO 10589，RFC 1195。 |
| 3. | 操作现场视察层 | OSPF 在 IP 层的顶部运行。 | 信息系统公司在 L2 运营。 |
| 4. | 支持的虚拟链接 | 是 | 不 |
| 5. | 灾难恢复/灾难恢复选举 | OSPF 在广播网络上选举 BDR 和 DR。 | 信息系统-信息系统在广播网络上选择单一的分布式信息系统。 |
| 6. | 知识产权连接 | OSPF 要求路由器之间的 IP 连接共享路由信息。 | IS-IS 不需要路由器之间的 IP 连接，因为更新是通过 CLNS 而不是 IP 发送的。 |
| 7. | 支持 | OSPF 支持 NBMA 和点到多点链路。 | IS-IS 不支持。 |
| 8. | 路由器区域 | OSPF 路由器可以属于多个区域。 | IS-IS 路由器只能属于一个区域。 |
| 9. | 区域/级别类型 | 主干区域标准区域(非主干区域) | 一级二级1/2 级区域 |
| 10. | 安全 | 容易受到攻击，因此需要更多的安全开销来提供保护。 | 因为，IS-IS 运行在 2 级，所以攻击的可能性极小。 |
| 11. | 识别 | OSPF 使用路由器 id 来识别网络中的路由器。 | IS-IS 使用系统标识来识别网络中的路由器。 |
| 12. | 灵活性 | 不如信息系统灵活。 | 使用起来比 OSPF 更灵活，尤其是在提供商领域。 |
| 13. | 表格刷新 | 30 分钟后，OSPF 会刷新整个路由表。 | IS-IS 不会像 OSPF 那样定期刷新整个 SPF 表。 |
| 14. | 相关术语 | 区域，非骨干区域，骨干区域，ABR，ASBR，主机。 | 信息系统，1 级，2 级，L1/L2，子域，专家系统。 |

</center>