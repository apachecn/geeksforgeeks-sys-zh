# 分布式系统中的同步

> 原文:[https://www . geesforgeks . org/分布式系统中的同步/](https://www.geeksforgeeks.org/synchronization-in-distributed-systems/)

[分布式系统](https://www.geeksforgeeks.org/design-issues-of-distributed-system/)是通过高速通信网络连接的计算机的集合。在分布式系统中，硬件和软件组件通过消息传递来通信和协调它们的动作。分布式系统中的每个节点都可以与其他节点共享资源。因此，需要适当分配资源，以保持资源状态，并帮助协调几个流程。为了解决这种冲突，使用了同步。分布式系统中的同步是通过时钟实现的。

物理时钟用于调整节点的时间。系统中的每个节点都可以与系统中的其他节点共享其本地时间。时间是根据世界协调时设定的。UTC 用作系统中节点的参考时钟。

时钟同步可以通过两种方式实现:外部和内部时钟同步。

1.  **External clock synchronization** is a clock with an external reference clock. It is used as a reference, and nodes in the system can set and adjust their time accordingly.
2.  **Internal clock synchronization** means that each node shares its time with other nodes, and all nodes set and adjust its time accordingly.

时钟同步算法有两种类型:集中式和分布式。

1.  **Centralized** refers to the time server. A single time server propagates its time to nodes, and all nodes adjust the time accordingly. It depends on a single time server, so if this node fails, the whole system will lose synchronization. Examples of centralization include Berkeley algorithm, passive time server, active time server and so on.
2.  **Distributed** There is no centralized time server. Instead, nodes adjust their time by using their local time, and then average the time difference with other nodes. Distributed algorithm overcomes the problems of scalability and single point of failure of centralized algorithm. Examples of distributed algorithms are global average algorithm, local average algorithm, network time protocol and so on.