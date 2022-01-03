# EIGRP 基础知识

> 原文:[https://www.geeksforgeeks.org/eigrp-fundamentals/](https://www.geeksforgeeks.org/eigrp-fundamentals/)

动态路由协议执行与静态路由协议相同的功能。在动态路由协议中，如果目的地不可达，则可以使用路由表中同一目的地的另一个条目。路由协议之一是 EIGRP。
**EIGRP:**
[增强型内部网关路由协议(EIGRP)](https://www.geeksforgeeks.org/computer-network-features-enhanced-interior-gateway-routing-protocol-eigrp/) 是一种动态路由协议，用于在任意两层 3 设备之间寻找最佳路径来传递数据包。EIGRP 工作在 OSI 模型的网络层协议上，使用 88 号协议。它使用度量来找出运行 EIGRP 的两个第 3 层设备(路由器或第 3 层交换机)之间的最佳路径。EIGRP 的管理距离是:-

<figure class="table">

| **EIGRP 路由** | **AD 值** |
| 汇总路线 | five |
| 内部路线 | Ninety |
| 外部路线 | One hundred and seventy |

它使用一些消息与运行 EIGRP 的邻居设备进行通信。这些是:-

1.  **Hello 消息-** 这些消息是保持活动的消息，在运行 EIGRP 的两个设备之间交换。如果有任何设备运行 EIGRP，或者有任何设备(运行 EIGRP)再次出现，这些消息用于邻居发现/恢复。
    如果在 224.0.0.10 多播，这些消息用于邻居发现。它包含 AS 数、k 值等值。
    单播时，这些消息用作确认。没有数据的问候被用作确认。
2.  **NULL update-**It is used to calculate SRTT(Smooth Round Trip Timer) and RTO(Retransmission Time Out). 
    *SRTT:* The time is taken by a packet to reach the neighboring router and the acknowledgment of the packet to reach the local router. 

    *RTO:* 如果组播失败，那么单播将被发送到该路由器。RTO 是本地路由器等待数据包确认的时间。

3.  **完全更新–**在交换问候消息之后或邻居形成之后，交换这些消息。此消息包含所有最佳路线。
4.  **部分更新-** 当拓扑发生变化并添加新链路时，会交换这些消息。它只包含新路线，而不是所有路线。这些消息是多播的。
5.  **查询消息-** 当设备被宣布死亡，并且在其拓扑表中没有到它的路由时，这些消息被多播。
6.  **回复消息–**这些消息是对发送给查询消息的发起者的查询消息的确认，陈述了查询消息中已经询问的到网络的路由。
7.  **Acknowledgement message** 
    It is used to acknowledge EIGRP updates, queries, and replies. Acks are hello packets that contain no data. 

    **注意:-** Hello 和确认数据包不需要任何确认。
    回复、查询、更新消息是可靠的消息，即需要确认。

**复合矩阵-**EIGRP 复合度量计算最多可以使用 5 个变量，但默认情况下只使用 2 个(K1 和 K3)。综合指标值为:

***K1(带宽)***
***K2(负载)***
***K3(延迟)***
***K4(可靠性)***
*T21】K5(MTU)*

为了计算成本，在复合矩阵中考虑沿着源和目的地之间的路径的最低带宽、负载、延迟、可靠性、MTU。
**注:-** 一般情况下，EIGRP 只使用 k1 和 k3 值进行度量计算。k1、k2、k3、k4、k5 的值分别为 10100。
**标准**要形成 EIGRP 邻居，应满足以下标准:-

1.  k 值应该匹配。
2.  自治系统号应该匹配。(自治系统是在单一管理控制下运行的一组网络)。
3.  身份验证应该匹配(如果适用)。EIGRP 仅支持 MD5 身份验证。
4.  子网掩码应该相同。

**计时器:-**
**Hello 计时器-**EIGRP 在接口上发送 Hello 消息的时间间隔。默认为 5 秒。
**死亡计时器-** 邻居无法发送 hello 数据包时被宣布死亡的时间间隔。默认为 15 秒。

</figure>