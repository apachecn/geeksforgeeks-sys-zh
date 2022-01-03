# 云计算中的八卦协议

> 原文:[https://www . geesforgeks . org/the-gossip-protocol-in-cloud-computing/](https://www.geeksforgeeks.org/the-gossip-protocol-in-cloud-computing/)

**八卦协议**是一种通信协议，它是进程计算机到计算机的通信，其工作原理与信息如何在社交网络上共享相同。如今，大多数系统经常使用流言协议来解决可能很难用其他方式解决的问题，要么是因为结构上的不便，要么是因为流言解决方案是最有效的解决方案。

现代分布式系统使用这种对等的八卦协议来确保信息被传播给网络中的所有成员。流言协议被称为**流行病协议**，因为它传播或传播数据的方式与流行病在生物栖息地传播病毒的方式相同。

八卦协议有三种主要类型:

1.  **传播协议:**
    这些协议也被称为造谣协议，因为它们使用流言蜚语在整个网络中传播信息，它们以产生最坏情况负载的方式向网络成员传播流言蜚语。

*   **反熵协议:**
    这些协议用于通过比较和修改比较来修复复制的数据。*   **Protocols that compute aggregates :**
    These protocols work by or compute an aggregate of the network by sampling information at the nodes and they combine the values to acquire a system-wide value – the largest value for some measurement nodes are making, smallest, etc.

    **云计算中 gossip 协议的实现:**
    Gossip 协议用于修复组播带来的问题；这是一种通信类型，在这种情况下，一条信息或流言从一个或多个节点发送到网络中的一组其他节点。当网络中的一组客户端同时需要相同的数据时，这很有用。但是在组播过程中会出现很多问题，如果接收端存在很多节点，延迟会增加；接收器接收多播的平均时间。

    为了在组中的期望目标之间获得这种多播消息或流言，流言协议周期性地向网络中的随机节点发送流言，一旦随机节点接收到流言，就被称为由于流言而被感染。现在，接收流言的随机节点与发送者做同样的事情，它向随机目标发送流言的多个副本。这个过程一直持续到目标节点获得多播为止。这个过程在将流言发送到随机节点后，将受感染的节点变成未受感染的节点。