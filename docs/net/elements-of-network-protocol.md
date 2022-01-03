# 网络协议要素

> 原文:[https://www.geeksforgeeks.org/elements-of-network-protocol/](https://www.geeksforgeeks.org/elements-of-network-protocol/)

**协议:**
管理数据通信的一组规则。

网络通信协议需要以下要素:

1.  **消息编码:**
    来自发送方的源消息被编码成信号或波，然后通过有线/无线介质传输，然后被接收和解码，消息被传递到目的地。编码是将一组 Unicode 字符转换成字节序列的过程。

    ```
    Message Source  –> Encoder  –> Transmitter –> Transmitter Medium –>
    Receiver –>Decoder –> Message destination
    ```

2.  **消息格式化和封装:**
    发送方和接收方有约定的格式。它封装信息以正确识别发送方和接收方。

消息格式取决于消息的类型和消息传递的媒介。
消息封装是一个过程，用于将一条消息放入另一条消息中，以便从源传输到目的地。

*   **Message size :**
    Here long messages must break into small pieces to travel across a network or The process of breaking up a long message into individual pieces before being sent over the network.

    **示例–**在手机短信中，将消息大小限制为 160 个正常字母字符。对于非字母字符，它需要 16 位数据来表示它们，大小限制为 70 个字符。

    *   **消息定时:**
    管理流量控制。确认响应超时。这需要某些定时控制信息。它检查数据传递中的任何延迟。它包括访问方法、流量控制、响应超时等规则。*   **Message delivery options :**
    There are different delivery options like Unicast, Multicast, Broadcast.

    向一个人发送信息被称为一对一传递，称为单播，这意味着只有一个目的地(单个目的地)。

    将信息传递给一个以上的人(同时是一组人)被称为一对多，并被称为多播，这意味着同一消息的一个发送者到多个目的地/接收者。

    有时信息要传达给同一地区的每个人。这被称为一对所有，称为广播，这意味着一个发送者向所有连接的接收者发送消息。