# 流量控制和拥塞控制的区别

> 原文:[https://www . geeksforgeeks . org/流量控制和拥塞控制的区别/](https://www.geeksforgeeks.org/difference-between-flow-control-and-congestion-control/)

**[流量控制](https://practice.geeksforgeeks.org/problems/what-is-flow-control-in-tcp)** 和 **[拥塞控制](https://www.geeksforgeeks.org/computer-networks-congestion-control/)** 都是不同情况下的流量控制方式。
流量控制和拥塞控制之间的主要区别在于，在流量控制中，控制从发送方流向接收方的流量。另一方面，在拥塞控制中，控制流量进入网络。

让我们看看流量控制和拥塞控制之间的区别:

| S.NO | 流控制 | 拥塞控制 |
| 1. | 在流量控制中，流量被控制从发送者流向接收者。 | 在这种情况下，控制流量进入网络。 |
| 2. | 数据链路层和传输层处理它。 | 网络层和传输层处理它。 |
| 3. | 在这种情况下，接收方的数据不会被淹没。 | 这样可以防止网络拥塞。 |
| 4. | 在流量控制中，只有发送方负责流量。 | 在这种情况下，传输层负责流量。 |
| 5. | 在这种情况下，通过发送方缓慢发送来阻止流量。 | 在这种情况下，传输层通过缓慢传输来阻止流量。 |
| 6. | 在流量控制中，缓冲区溢出在接收器中受到限制。 | 在拥塞控制中，缓冲区溢出被限制在网络的中间系统中。 |