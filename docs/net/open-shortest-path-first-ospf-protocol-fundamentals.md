# 开放最短路径优先(OSPF)协议基础

> 原文:[https://www . geesforgeks . org/open-最短路径优先-OSPF-protocol-foundations/](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-protocol-fundamentals/)

开放最短路径优先(OSPF)是一种**链路状态路由协议**，用于使用自己的最短路径优先(SPF)算法找到源路由器和目的路由器之间的最佳路径。链路状态路由协议是一种使用触发式更新概念的协议，即如果在获知的路由表中观察到变化，则仅触发更新，而不像距离矢量路由协议那样在一段时间内交换路由表。

开放最短路径优先(OSPF)是由互联网工程任务组(IETF)开发的内部网关协议(IGP)之一，即旨在大型自治系统或路由域内移动数据包的协议。它是一个**网络层协议**，工作在协议号 89 上，使用 AD 值 110。OSPF 使用多播地址 224.0.0.5 进行正常通信，使用 224.0.0.6 更新指定路由器(DR)/备用指定路由器(BDR)。

**标准–**
要在 OSPF 形成邻居关系，两台路由器都有一个标准:

1.  它应该出现在同一个区域。
2.  我认为路由器是独一无二的。
3.  子网掩码应该相同。
4.  你好，死亡计时器应该是一样的。
5.  存根标志必须匹配。
6.  身份验证必须匹配。

OSPF 支持空值、纯文本、MD5 身份验证。

**注意–**两台路由器(邻居)都应该启用某种类型的身份验证。例如，如果一个邻居启用了 MD5 身份验证，那么其他邻居也应该启用 MD5 身份验证。

**OSPF 消息–**
OSPF 使用某些消息在运行 OSPF 的路由器之间进行通信。

*   **Hello 消息–**
    这些是用于邻居发现/恢复的保活消息。这些每 10 秒交换一次。这包括以下信息:路由器标识、你好/死亡间隔、区域标识、路由器优先级、灾难恢复和 BDR IP 地址、身份验证数据。
*   **数据库描述(DBD)–**
    是路由器的 OSPF 路由。这包含一个自治系统或一个区域(路由域)的拓扑。
*   **链路状态请求(LSR)–**
    当路由器收到 DBD 时，会将其与自己的 DBD 进行比较。如果 DBD 收到的更新比它自己的 DBD 多，那么 LSR 将被发送给它的邻国。
*   **链路状态更新(LSU)–**
    当路由器收到 LSR 时，它会以包含请求的详细信息的 LSU 消息进行响应。
*   **链路状态确认–**
    这为链路状态交换过程提供了可靠性。它作为 LSU 的确认发送。
*   **链路状态通告(LSA)–**
    它是一个 OSPF 数据包，包含链路状态路由信息，只与已经形成邻接关系的路由器共享。

**注意–**链路状态通告和链路状态确认都是不同的消息。

**计时器–**

*   **Hello 计时器–**
    OSPF 路由器在接口上发送 Hello 消息的时间间隔。默认为 10 秒。
*   **死亡计时器–**
    邻居无法发送 hello 数据包时被宣布死亡的时间间隔。默认为 40 秒。它通常是 hello 间隔的 4 倍，但可以根据需要手动配置。

**OSPF 支持/提供/优势–**

*   IPv4 和 IPv6 路由协议
*   使用相同目的地的等价路由进行负载平衡
*   VLSM 和路线总结
*   无限跳数
*   触发更新以实现快速收敛
*   一种采用 SPF 算法的无环拓扑
*   运行在大多数路由器上
*   无类协议

像 OSPF 有一些缺点，它需要一个额外的中央处理器进程来运行 SPF 算法，需要更多的内存来存储邻接拓扑，并且设置更复杂，难以排除故障。