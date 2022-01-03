# 数据链路层的设计问题

> 原文:[https://www . geesforgeks . org/数据链路层设计问题/](https://www.geeksforgeeks.org/design-issues-in-data-link-layer/)

前提–[OSI 模型的层](https://www.geeksforgeeks.org/layers-of-osi-model/)
[**数据链路层**](https://www.geeksforgeeks.org/data-link-layer-in-osi-model/) 是物理层之后的第二层。数据链路层负责维护两台主机或节点之间的数据链路。

在讨论数据链路层的设计问题之前。它的一些子层及其功能如下。

数据链路层分为两个子层:

1.  [**逻辑链路控制子层(LLC)**](https://practice.geeksforgeeks.org/problems/what-is-logical-link-control)**–**
    为数据链路提供逻辑，从而控制数据链路层的同步、流量控制和错误检查功能。功能有–
    *   **(i)** 错误恢复。
    *   **(ii)** 执行流量控制操作。
    *   **(三)**用户寻址。

2.  [**【媒体访问控制子层】**](https://practice.geeksforgeeks.org/problems/what-is-media-access-controlmac)**–**
    是数据链路层的第二个子层。它控制传输介质的流量和复用。数据包的传输由这一层控制。该层负责通过网络接口卡发送数据。
    功能是–
    *   **(i)** 执行对媒体访问的控制。
    *   **(ii)** 它对直接连接到局域网的站点执行唯一寻址。
    *   **(iii)** 错误检测。

**数据链路层的设计问题有:**

1.  **提供给网络层的服务–**
    数据链路层充当[网络层](https://www.geeksforgeeks.org/design-issues-in-network-layer/)的服务接口。主要服务是将数据从发送机器的网络层传输到目的机器的网络层。这种传输也通过动态链接库进行。
2.  [**帧同步**](https://www.geeksforgeeks.org/framing-in-data-link-layer/)**–**
    源机器以称为帧的块的形式向目的机器发送数据。应该识别每个帧的开始和结束，以便目的机器能够识别该帧。
3.  **流量控制–**
    流量控制是为了防止数据帧在接收端的流动。源机器发送数据帧的速度不能快于目标机器接受数据帧的能力。
4.  **错误控制–**
    进行错误控制是为了防止帧重复。在从源机器传输到目的机器的过程中引入的错误必须在目的机器上检测和纠正。