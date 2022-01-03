# 停止和等待、返回和选择性重复之间的差异

> 原文:[https://www . geesforgeks . org/stop-and-wait-gobackn-and-selected-repeat/](https://www.geeksforgeeks.org/difference-between-stop-and-wait-gobackn-and-selective-repeat/)的区别

可靠的数据传输是计算机网络的主要关注点之一。这个服务部门掌握在 [TCP](https://www.geeksforgeeks.org/computer-network-tcpip-model/) 手中。他们的主要流量控制协议——停止和等待、返回和选择性重复。

1.  [**停止并等待**](https://www.geeksforgeeks.org/stop-and-wait-arq/)**–**
    发送方发送数据包并等待数据包的确认(ACK)。一旦确认到达发送方，它将连续发送下一个数据包。如果没有收到确认，它会重新发送前一个数据包。

2.  [**返回 N**](https://www.geeksforgeeks.org/sliding-window-protocol-set-2-receiver-side/)**–**
    发送方发送 N 个数据包，与窗口大小相等。一旦发送了整个窗口，发送方就等待累积的确认来发送更多的数据包。在接收端，它只接收有序数据包，丢弃无序数据包。在数据包丢失的情况下，整个窗口将被重新传输。

3.  [**【选择性重复】**](https://www.geeksforgeeks.org/sliding-window-protocol-set-3-selective-repeat/)**–**
    发送方发送窗口大小为 N 的数据包，接收方确认所有数据包是否按顺序接收。在这种情况下，接收器维护一个缓冲区来包含乱序数据包并对其进行排序。发送方有选择地重新发送丢失的数据包，并向前移动窗口。

**差异:**T2】

| 性能 | 停下来等待 | 后退 | 选择性重复 |
| --- | --- | --- | --- |
| 发件人窗口大小 | one | 普通 | 普通 |
| 接收器窗口大小 | one | one | 普通 |
| 最小序列号 | Two | N+1 | 2N |
| 效率 | 1/(1+2*a) | N/(1+2*a) | N/(1+2*a) |
| 确认的类型 | 个人 | 累积的 | 个人 |
| 接收端支持的订单 | – | 仅订单交货 | 无序交付也是如此 |
| 数据包丢失时的重传次数 | one | 普通 | one |

其中，

*   a =传播延迟和传输延迟之比，
*   在 N=1 时，返回 N 有效地减少为停止和等待，/li>

*   当“返回”N 累计确认打包的数据包时，它会拒绝无序的数据包，
*   由于选择性重复支持接收无序数据包(它在接收数据包后对窗口进行排序)，因此它使用独立确认来确认数据包。

**参考–**
[**<u>书籍–</u>**](https://amzn.to/3hfQerb)计算机网络