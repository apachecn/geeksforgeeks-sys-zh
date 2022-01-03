# TCP 标志

> 原文:[https://www.geeksforgeeks.org/tcp-flags/](https://www.geeksforgeeks.org/tcp-flags/)

在 TCP 连接中，标志用于指示特定的连接状态，或者提供一些额外的有用信息，如故障排除，或者处理对特定连接的控制。最常用的标志是**“SYN”、“ACK”和“FIN”**。每个标志对应 1 位信息。

**旗帜类型:**

*   **同步(SYN)–**用于[连接建立](https://www.geeksforgeeks.org/computer-network-tcp-connection-establishment/)阶段的第一步或两台主机之间的三次握手过程。只有来自发送方和接收方的第一个数据包应该设置此标志。这用于同步序列号，即告诉另一端他们应该接受哪个序列号。
*   **确认(ACK)–**用于确认主机成功接收的数据包。如果确认号字段包含有效的确认号，则设置该标志。
    在下图中，接收方在连接建立的第二步发送确认= 1 和同步= 1，告知发送方它收到了初始数据包。

*   **Finish(FIN)–**用于请求[连接终止](https://www.geeksforgeeks.org/computer-network-tcp-connection-termination/)，即当发送方没有数据时，请求连接终止。这是发送方发送的最后一个数据包。它释放保留的资源，并优雅地终止连接。

*   **Reset(RST)–**如果 RST 发送方觉得 TCP 连接有问题或者对话不应该存在，则用于终止连接。当数据包被发送到不期望它的特定主机时，它可以从接收端获得发送。

**完成(FIN) v/s 复位(RST)–**T2】

![](img/2eb2344cbc5a21af997e2db839e21465.png)

*   **Push (PSH) –** Transport layer by default waits for some time for application layer to send enough data equal to maximum segment size so that the number of packets transmitted on network minimizes which is not desirable by some application like interactive applications(chatting). Similarly transport layer at receiver end buffers packets and transmit to application layer if it meets certain criteria. 

    这个问题是用 PSH 解决的。传输层将 PSH 设置为 1，并在收到应用层的信号后立即将数据段发送到网络层。接收方传输层在看到 PSH = 1 时，立即将数据转发到应用层。
    一般来说，它告诉接收方在收到这些数据包时处理它们，而不是缓冲它们。

*   **紧急(URG)–**带有 URG = 1 标志的数据段内的数据会立即转发到应用层，即使还有更多数据要给应用层。它用于通知接收方在处理所有其他数据包之前处理紧急数据包。当收到所有已知的紧急数据时，将通知接收者。

**推送(PSH)紧急(URG)–**T2】

![](img/f6e3084b6f131da70e69cd06d46a243d.png)