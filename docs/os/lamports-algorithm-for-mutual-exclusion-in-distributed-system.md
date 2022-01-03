# 分布式系统中的 Lamport 互斥算法

> 原文:[https://www . geesforgeks . org/lamports-分布式系统中互斥算法/](https://www.geeksforgeeks.org/lamports-algorithm-for-mutual-exclusion-in-distributed-system/)

先决条件:[分布式系统中的互斥](https://www.geeksforgeeks.org/operating-system-mutual-exclusion-in-distributed-system/)
**Lamport 的分布式互斥算法**是 Lamport 提出的基于权限的算法，作为他的分布式系统同步方案的说明。
基于权限的时间戳用于对关键部分请求进行排序，并解决请求之间的任何冲突。

在 Lamport 的算法中，关键部分请求按时间戳的递增顺序执行，即时间戳较小的请求将比时间戳较大的请求获得先执行关键部分的权限。

在该算法中:

*   使用三种类型的消息(**请求**、**回复**和**释放**)，并且通信通道假定遵循先进先出顺序。
*   一个站点向所有其他站点发送 **REQUEST** 消息，以获得它们进入临界区的许可。
*   一个站点向请求站点发送**回复**消息，请求站点允许其进入临界区。
*   一个站点在退出关键部分时向所有其他站点发送 **RELEASE** 消息。
*   每个站点 S <sub>i</sub> 都保持一个队列来存储按时间戳排序的关键部分请求。
    **request _ queue<sub>I</sub>**表示站点 S <sub>i</sub> 的队列
*   使用 Lamport 的逻辑时钟给每个关键部分请求一个时间戳。
*   时间戳用于确定关键部分请求的优先级。时间戳越小，优先级越高。关键部分请求的执行总是按照时间戳的顺序。

**算法:**

*   **进入临界区:**
    *   当一个站点 S <sub>i</sub> 想要进入临界区时，它向所有其他站点发送请求消息 **Request(ts <sub>i</sub> ，i)** ，并将该请求置于 **request_queue <sub>i</sub>** 上。这里，Ts <sub>i</sub> 表示站点 S <sub>i</sub> 的时间戳
    *   When a site S<sub>j</sub> receives the request message **REQUEST(ts<sub>i</sub>, i)** from site S<sub>i</sub>, it returns a timestamped REPLY message to site S<sub>i</sub> and places the request of site S<sub>i</sub> on **request_queue<sub>j</sub>**

        。

*   **执行临界区:**
    *   如果站点 S <sub>i</sub> 已经从所有其他站点接收到时间戳大于 **(ts <sub>i</sub> ，i)** 的消息，并且它自己的请求位于 **request_queue <sub>i</sub>** 的顶部，则它可以进入临界区
*   **释放临界区:**
    *   当站点 S <sub>i</sub> 退出临界区时，它从其请求队列的顶部移除自己的请求，并向所有其他站点发送一个带有时间戳的 **RELEASE** 消息
    *   当站点 S <sub>j</sub> 从站点 S <sub>i</sub> 接收到带有时间戳的 **RELEASE** 消息时，它将从其请求队列中移除 S <sub>i</sub> 的请求

**消息复杂性:**
兰伯特的算法要求每个关键部分执行调用 3(N-1)条消息。这 3(N-1)条信息包括

*   (N-1)条请求消息
*   (N-1)条回复消息
*   (N-1)发布消息

**兰波特算法的缺点:**

*   **不可靠的方法:**任何一个进程的失败都会导致整个系统的进程停止。
*   **高消息复杂度:**算法要求每个关键部分调用 3(N-1)条消息。

**性能:**

*   同步延迟等于最大消息传输时间
*   每次 CS 执行需要 3(N–1)条消息。
*   在某些情况下，通过省略**回复**消息，算法可以优化为 2(N–1)条消息。