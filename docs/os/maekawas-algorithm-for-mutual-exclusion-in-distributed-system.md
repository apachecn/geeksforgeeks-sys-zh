# 分布式系统中的前川互斥算法

> 原文:[https://www . geesforgeks . org/Mae kawa s-分布式系统中互斥算法/](https://www.geeksforgeeks.org/maekawas-algorithm-for-mutual-exclusion-in-distributed-system/)

先决条件–[分布式系统中的互斥](https://www.geeksforgeeks.org/operating-system-mutual-exclusion-in-distributed-system/)
**前川算法**是基于法定人数的方法，用于确保分布式系统中的互斥。众所周知，在基于权限的算法中，如兰波特算法、里克特-阿格拉瓦拉算法等。一个站点请求来自每一个其他站点的许可，但是在基于法定人数的方法中，一个站点不请求来自每一个其他站点的许可，而是请求来自被称为**法定人数**的站点子集的许可。

在该算法中:

*   使用三种类型的消息(**请求**、**回复**和**释放**)。
*   一个站点发送一个 **REQUEST** 消息给它请求集中的所有其他站点或法定人数，以获得他们进入临界区的许可。
*   一个站点向请求站点发送**回复**消息，请求站点允许其进入临界区。
*   一个站点在退出关键部分时，向其请求集或法定人数中的所有其他站点发送 **RELEASE** 消息。

**请求集或法定人数的构造:**
前川算法中的请求集或法定人数必须满足以下属性:

1.  ```
    ∀i ∀j : i ≠ j, 1 ≤ i, j ≤ N :: Ri ⋂ Rj ≠ ∅ 
    ```

    **即**任意两个站点的请求集之间至少有一个公共站点。

2.  ```
    ∀i : 1 ≤ i ≤ N :: Si ∊ Ri 
    ```

3.  ```
    ∀i : 1 ≤ i ≤ N :: |Ri| = K 
    ```

4.  任何地点 S <sub>i</sub> 都包含在正好 K 个集合中。
5.  ```
    N = K(K - 1) +1 and |Ri| = √N 
    ```

**算法:**

*   **进入临界区:**
    *   当站点 S <sub>i</sub> 想要进入临界区时，它向请求集中的所有其他站点发送请求消息**REQUEST(I)****R<sub>I</sub>**。
    *   When a site S<sub>j</sub> receives the request message **REQUEST(i)** from site S<sub>i</sub>, it returns a **REPLY** message to site S<sub>i</sub> if it has not sent a **REPLY** message to the site from the time it received the last **RELEASE** message. Otherwise, it queues up the request.

        。

*   **执行临界区:**
    *   如果站点 S <sub>i</sub> 已经从请求集中的所有站点接收到**回复**消息 **R <sub>i</sub>**
*   **释放临界区:**
    *   当站点 S <sub>i</sub> 退出临界区时，它会向请求集中的所有其他站点发送 **RELEASE(i)** 消息 **R <sub>i</sub>**
    *   当站点 S <sub>j</sub> 从站点 S <sub>i</sub> 接收到 **RELEASE(i)** 消息时，它发送 **REPLY** 消息到队列中等待的下一个站点，并从队列中删除该条目
    *   在队列为空的情况下，站点 S <sub>j</sub> 更新其状态，以表明自从收到最后一条 **RELEASE** 消息以来，它没有发送任何 **REPLY** 消息

**消息复杂性:**
前川算法要求每个关键部分执行调用 3√N 个消息，因为请求集的大小为√N。这 3√N 个消息涉及。

*   √N 条请求消息
*   √N 封回复邮件
*   √N 条发布消息

**前川算法的缺点:**

*   这种算法容易出现死锁，因为一个站点被其他站点独占锁定，并且请求没有按其时间戳排列优先级。

**性能:**

*   同步延迟等于消息传播延迟时间的两倍
*   每个关键部分执行需要 3√n 条消息。