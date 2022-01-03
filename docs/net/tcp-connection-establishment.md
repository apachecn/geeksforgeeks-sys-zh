# TCP 连接建立

> 原文:[https://www.geeksforgeeks.org/tcp-connection-establishment/](https://www.geeksforgeeks.org/tcp-connection-establishment/)

先决条件–[TCP 三次握手过程](https://www.geeksforgeeks.org/computer-network-tcp-3-way-handshake-process/)
TCP 是一个面向连接的协议，每个面向连接的协议都需要建立连接，以便在通信两端预留资源。

**连接建立–**

1.发件人从以下内容开始流程:

*   **序列号(Seq=521):** 包含发送方生成的随机初始序列号。
*   **同步标志(同步=1):** 请求接收器将其序列号与上述序列号同步。
*   **最大段大小(MSS=1460 B):** 发送方告知其最大段大小，以便接收方发送不需要任何分片的数据报。MSS 字段存在于 TCP 报头的**选项**字段中。
*   **窗口大小(window=14600 B):** 发送者告知他的缓冲容量，他必须在其中存储来自接收者的消息。

2.TCP 是一种全双工协议，因此发送方和接收方都需要一个窗口来接收对方的消息。

*   **序列号(Seq=2000):** 包含接收端生成的随机初始序列号。
*   **Syn 标志(Syn=1):** 请求发送方将其序列号与上面提供的序列号同步。
*   **最大段大小(MSS=500 B):** 发送方告知其最大段大小，以便接收方发送不需要任何碎片的数据报。MSS 字段存在于 TCP 报头的**选项**字段中。
    自 MSS <sub>接收方</sub> < MSS <sub>发送方</sub>起，双方约定最小 MSS，即 500 B，避免两端包碎片。

    ```
    Therefore, receiver can send maximum of 14600/500 = 29 packets.
    This is the receiver's sending window size.
    ```

*   **窗口大小(窗口=10000 B):** 接收者告诉他的缓冲容量，他必须在其中存储来自发送者的消息。

    ```
    Therefore, sender can send a maximum of 10000/500 = 20 packets.
    This is the sender's sending window size.
    ```

*   **确认号(确认号=522):** 由于序列号 521 被接收器 so 接收，所以它请求确认号=522 的下一个序列号，这是接收器期望的下一个分组，因为 Syn 标志消耗 1 个序列号
*   **确认标志(ACk=1):** 表示确认号字段包含接收器预期的下一个序列。

3.发送方通过以下方式对连接建立做出最终回复:

*   **序列号(Seq=522):** 由于序列号= 1 中的 521<sup>ST</sup>步骤和 SYN 标志消耗一个序列号，因此下一个序列号将是 522。
*   **确认号(确认号=2001):** 由于发送方正在确认序列号为 2000 的来自接收方的 SYN=1 数据包，因此下一个序列号应为 2001。
*   **确认标志(确认=1):** 表示确认号字段包含发送方期望的下一个序列。

![](img/830b0da0a7c2ea8f63c7ccc7941794d7.png)

由于 TCP 的连接建立阶段使用了 3 个数据包，所以也被称为 [3 路握手](https://www.geeksforgeeks.org/computer-network-tcp-3-way-handshake-process/)T2(SYN，SYN + ACK，ACK)。

*   **GATE 问题–**[GATE IT 2008 |问题 67](https://www.geeksforgeeks.org/gate-gate-it-2008-question-67/)

相关下一篇文章–[TCP 连接终止](https://www.geeksforgeeks.org/computer-network-tcp-connection-termination/)