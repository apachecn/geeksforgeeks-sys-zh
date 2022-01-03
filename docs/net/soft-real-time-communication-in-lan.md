# 局域网内软实时通信

> 原文:[https://www . geesforgeks . org/soft-实时-局域网内通信/](https://www.geeksforgeeks.org/soft-real-time-communication-in-lan/)

**软实时通信**是用于支持软实时应用的通信系统，是局域网。软实时通信网络不能为应用提供绝对的[服务质量](https://www.geeksforgeeks.org/quality-of-service-qos-in-atm/)(服务质量)保证。这些网络始终确保优先处理实时消息。它还确保实时消息的消息截止期未命中比率保持在最小，并且可以为实时消息提供延迟界限的统计保证。

**软实时通信中的协议:**
软实时通信中使用的协议通常假设软实时和硬实时消息都在网络上传输。通常，假设软实时流量由 CBR 和 VBR 来源组成。还假设软实时消息速率与信道容量相比非常低。硬实时消息不定期地以突发形式到达。在突发情况下，很难保证实时流量。因此，需要对突发进行平滑处理，以确保实时消息的截止日期具有持久的统计保证。

**软实时通信算法:**
软实时通信采用固定速率流量平滑算法。固定速率流量平滑算法由 **Kweon** 和 **Shin** 开发。它基于网络范围的传输限制。系统中每个节点的输入限制是从传输限制中导出的。流量平滑器放置在 MAC 层和 [TCP/IP](https://www.geeksforgeeks.org/tcp-ip-model/) 层之间。它用于平滑硬实时系统，从而保证实时消息不会被破坏。流量平滑算法就像一个漏桶算法，被称为信用桶深度(CBD)。它有两个静态固定参数“信用时段深度”和“刷新周期”。

*   **信用桶深度(CBD)–**
    CBD 是每次刷新时添加到桶中的最大信用数量。它还表示一个存储桶可以容纳的最大学分数。

*   **Refresh Period (RP) –**
    RP is refresh period with which bucket is filled with new credits.

    **工作:**
    CBD/RP 比值是非实时消息的平均保证吞吐量。桶中的信用点数称为当前网络份额。当可用信用的数量为正，但小于要发送的消息的大小时，就借用信用。因此，信用余额随时可能变成负数。如果贷项被借用，当前网络份额可能变为负数。每次刷新时都会更新存储桶中的信用点数，即当前网络份额。

    ```
    CNS = min (CNS + CBD, CBD)
    ```

    《生物多样性公约》的信用额是这样填写的，即国家赔偿额不超过《生物多样性公约》。当硬实时消息从 TCP/IP 层到达时，执行平滑过程。

    ```
    if (CNS > 0)
         CNS = CNS - messageBytes
         /* where messageBytes is size of
            the message */
         transmit the message
    else
         hold the message in buffer until CNS > 0

    ```