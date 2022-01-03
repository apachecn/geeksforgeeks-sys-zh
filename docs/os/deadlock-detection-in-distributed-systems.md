# 分布式系统中的死锁检测

> 原文:[https://www . geesforgeks . org/分布式系统死锁检测/](https://www.geeksforgeeks.org/deadlock-detection-in-distributed-systems/)

在分布式系统中，死锁既无法防止也无法避免，因为系统非常庞大，不可能避免。因此，只能实现死锁检测。分布式系统中的死锁检测技术要求如下:

*   **Progress–**
    该方法应该能够检测到系统中的所有死锁。
*   **安全–**
    该方法不应检测到虚假或幻影死锁。

有三种方法可以检测分布式系统中的死锁。它们如下:

1.  **集中式方法–**
    在集中式方法中，只有一个负责的资源来检测死锁。这种方法的优点是简单且易于实现，而缺点包括一个节点的工作负载过大、单点故障(即如果该节点出现故障，整个系统将依赖于一个节点，整个系统将崩溃)，这反过来又会降低系统的可靠性。

2.  **分布式方法–**
    在分布式方法中，不同的节点协同工作来检测死锁。没有单点故障(即整个系统依赖于一个节点，如果该节点出现故障，整个系统就会崩溃)，因为工作负载在所有节点之间平均分配。死锁检测的速度也会提高。

3.  **分层法–**
    这种方法最有优势。它是分布式系统中集中式和分布式死锁检测方法的结合。在这种方法中，一些选定的节点或节点集群负责死锁检测，并且这些选定的节点由单个节点控制。