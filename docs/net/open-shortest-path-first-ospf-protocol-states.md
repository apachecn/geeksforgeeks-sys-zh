# 开放最短路径优先(OSPF)协议状态

> 原文:[https://www . geesforgeks . org/open-最短路径优先-ospf-protocol-states/](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-protocol-states/)

先决条件–[OSPF 基础知识](https://www.geeksforgeeks.org/computer-network-open-shortest-path-first-ospf-protocol-fundamentals/)
开放最短路径优先(OSPF)是一种链路状态路由协议，用于使用自己的最短路径优先(最短路径优先)在源路由器和目的路由器之间找到最佳路径。OSPF 是由互联网工程任务组(IETF)开发的内部网关协议(IGP)之一，即旨在大型自治系统或路由域内移动数据包的协议。它是一个网络层协议，工作在协议号 89 上，使用 AD 值 110。OSPF 使用多播地址 224.0.0.5 进行正常通信，使用 224.0.0.6 更新指定路由器(DR)/备用指定路由器(BDR)。

**OSPF 术语–**

1.  **路由器 I–**这是路由器上最高的活动 IP 地址。首先，考虑最高环回地址。如果没有配置环回，则考虑路由器接口上的最高活动 IP 地址。

2.  **路由器优先级–**这是分配给运行 OSPF 的路由器的 8 位值，用于在广播网络中选择 DR 和 BDR。

3.  **指定路由器(DR)–**选择它是为了最大限度地减少形成的邻接的数量。灾难恢复将本地存储分配给所有其他路由器。在所有其他路由器共享 DBD 的广播网络中，选择灾难恢复。在广播网络中，路由器请求对灾难恢复进行更新，灾难恢复将使用更新来响应该请求。

4.  **备份指定路由器(BDR)–**BDR 是广播网络中 DR 的备份。当灾难恢复停止时，BDR 成为灾难恢复并执行其功能。

**DR 和 BDR 选举–**DR 和 BDR 选举在广播网络或多址网络中进行。以下是选举的标准:

1.  具有最高路由器优先级的路由器将被声明为 dr

2.  如果路由器优先级有关联，那么我会考虑最高的路由器。首先，考虑最高环回地址。如果没有配置环回，则考虑路由器接口上的最高活动 IP 地址。

**OSPF 状态–**操作 OSPF 的设备会经历某些状态。这些状态是:

1.  **Down–**在这种状态下，接口上没有收到 hello 数据包。
    **注意–**下行状态并不意味着接口物理下行。在这里，这意味着 OSPF 邻接进程尚未开始。

2.  **INIT–**在这种状态下，已经从另一台路由器接收到 hello 数据包。

3.  **2WAY–**在 2WAY 状态下，两台路由器都收到了来自其他路由器的 hello 数据包。双向连接已经建立。
    **注–**在 2WAY 状态和 Exstart 状态之间，进行 DR 和 BDR 选举。

4.  **Exstart–**在这种状态下，交换空 DBD。在这个州，主人和奴隶的选举发生。拥有较高路由器的路由器我将成为主路由器，而另一个路由器将成为从路由器。本次选举决定哪台路由器将首先发送其 DBD(已形成邻居的路由器将参加本次选举)。

5.  **交换–**在这种状态下，实际的 DBD 被交换。

6.  **加载–**在这种状态下，交换 LSR、LSU 和 LSA(链路状态确认)。
    **重要提示–**当一台路由器从另一台路由器接收到 DBD 时，它会将自己的 DBD 与另一台路由器 DBD 进行比较。如果接收到的 DBD 比它自己的 DBD 更新，那么路由器会将 LSR 发送到另一个路由器，说明需要哪些链路。另一台路由器回复包含所需更新的 LSU。作为回报，路由器会回复链路状态确认。

7.  **Full–**在这种状态下，所有信息都会同步。OSPF 路由只能在“已满”状态后开始。