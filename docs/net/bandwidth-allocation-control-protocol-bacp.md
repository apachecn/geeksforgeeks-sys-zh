# 带宽分配控制协议(BACP)

> 原文:[https://www . geesforgeks . org/带宽-分配-控制-协议-bacp/](https://www.geeksforgeeks.org/bandwidth-allocation-control-protocol-bacp/)

**带宽分配控制协议(BACP)** 通常允许与数据呼叫的另一方进行协商，以简单地请求进行额外的呼叫，从而提高和增加数据吞吐量的效率。BACP 基本上为[点对点协议](https://www.geeksforgeeks.org/point-to-point-protocol-ppp-phase-diagram/)多链路协议如何运行提供了动态控制机制。它通常使用与中定义的链路控制协议(LCP)类似的数据包交换机制。它基本上是为了管理和处理通常支持 PPP 多链路协议的动态带宽分配而设计的。

**BACP 功能:**

1.  BACP 通常允许实现多链路互操作，即通过使用链路类型、速度甚至电话号码来提供呼叫控制，从而一起操作或工作。
2.  它还为 IETF 的多链路 PPP 增加了一些附加功能。
3.  它提供了一种灵活而健壮的方式来处理和控制两个对等体或客户端之间的带宽。
4.  它通常控制由链接在很短或很短的时间内被启动和删除引起的抖动。
5.  它还确保在添加或删除 MP 捆绑包中的一个或多个连接时，通知并指示链接或连接的两端。

**BACP 命令:**
还有几个 BACP 命令。其中一些如下:

<center>

| 命令 | 描述 |
| --- | --- |
| ppp bap 呼叫 | 用于启用 PPP BACP 回拨和设置回拨参数。 |
| ppp bap 回调 | 用于设置参数，仅用于从多功能包中删除链接或连接。 |
| ppp bap 链接类型 | 用于确定和指定特定 MP 捆绑包中可能添加的不同链接类型。 |
| 最大购买力平价 | 用于设置和管理 BACP 重传次数的上限。 |
| ppp bap 监控负载 | 用于根据 MP Bundle 的当前负载澄清和检查客户端或对等方添加或删除链接或连接的请求，并定义拨号器负载阈值。 |
| ppp 多重连结 | 用于在接口上启用和允许 MLP(多链路 PPP)，并可选地启用和允许动态带宽分配。 |
| 显示 ppp 多链接 | 用于显示 MLP 包的信息或包数据。 |

**BACP 表头格式:**
BACP 由以下 4 个字段组成:

![](img/b8238c7cf35f240fd202587cd855527d.png)

1.  **Code field –**
    This field is of 8 bits. It is basically required to determine the type of function that is needed to be performed. There are various types of functions that can be performed. These functions are given below with their specific code :

    <center>

    | 密码 | 描述 |
    | --- | --- |
    | one | 配置-请求 |
    | Two | 配置确认 |
    | three | 配置-Nak |
    | four | 配置-拒绝 |
    | five | 终止-请求 |
    | six | 终止-Ack |
    | seven | 代码-拒绝 |

    </center>

2.  **标识符字段–**
    该字段为 8 位，基本上用于识别和匹配所有请求和回复。
3.  **长度字段–**
    该字段通常为 16 位。
4.  **数据字段–**
    该字段不是恒定的，因为它的长度不同。

</center>