# 分布式系统互斥中的 Ricart-agr awala 算法

> 原文:[https://www . geeksforgeeks . org/ricart-agr awala-分布式系统中的互斥算法/](https://www.geeksforgeeks.org/ricart-agrawala-algorithm-in-mutual-exclusion-in-distributed-system/)

先决条件:[分布式系统中的互斥](https://www.geeksforgeeks.org/operating-system-mutual-exclusion-in-distributed-system/)
**Ricart–Agrawala 算法**是由 Glenn Ricart 和 Ashok Agrawala 提出的一种在分布式系统中形成互斥的算法。该算法是 Lamport 分布式互斥算法的扩展和优化。和 Lamport 的算法一样，它也遵循基于权限的方法来确保互斥。

在该算法中:

*   使用两种类型的消息(**请求**和**回复**，并且通信信道假定遵循先进先出顺序。
*   一个站点向所有其他站点发送 **REQUEST** 消息，以获得它们进入临界区的许可。
*   一个站点向另一个站点发送 **REPLY** 消息，允许其进入临界区。
*   使用 Lamport 的逻辑时钟给每个关键部分请求一个时间戳。
*   时间戳用于确定关键部分请求的优先级。时间戳越小，优先级越高。关键部分请求的执行总是按照时间戳的顺序。

**算法:**

*   **进入临界区:**
    *   当一个站点 S <sub>i</sub> 想要进入临界区时，它会向所有其他站点发送一个带有时间戳的 **REQUEST** 消息。
    *   当站点 S <sub>j</sub> 从站点 S <sub>i</sub> 接收到**请求**消息时，如果且仅当
        *   站点 S <sub>j</sub> 既没有请求也没有当前正在执行关键部分。
        *   In case Site S<sub>j</sub> is requesting, the timestamp of Site S<sub>i</sub>‘s request is smaller than its own request.

            否则，请求将被站点 S <sub>j</sub> 延迟。

*   **执行临界区:**
    *   站点 S <sub>i</sub> 如果收到了所有其他站点的**回复**消息，则进入临界区。
*   **释放临界区:**
    *   退出站点 S <sub>后，我</sub>向所有延迟的请求发送**回复**消息。

**消息复杂度:**
Ricart–Agrawala 算法要求每个关键部分执行调用 2(N–1)条消息。这 2(N-1)条信息包括

*   (N-1)条请求消息
*   (N-1)条回复消息

**Ricart-agr awala 算法的缺点:**

*   **不可靠的方法:**系统中任何一个节点出现故障，都会导致系统进程停顿。在这种情况下，这个过程将永远挨饿。
    节点故障的问题可以通过超时后检测故障来解决。

**性能:**

*   同步延迟等于最大消息传输时间
*   每个关键部分执行需要 2(N-1)条消息