# 传输层的 TCP 和 UDP

> 原文:[https://www . geesforgeks . org/TCP-and-UDP-in-transport-layer/](https://www.geeksforgeeks.org/tcp-and-udp-in-transport-layer/)

第 3 层或网络层使用 IP 或互联网协议，这是一种无连接协议，单独处理每个数据包，导致传输过程中缺乏可靠性。例如，当数据从一台主机发送到另一台主机时，每个数据包可能会采用不同的路径，即使它属于同一会话。这意味着数据包可能/可能没有以正确的顺序到达。因此，IP 依靠更高层的协议来提供可靠性。

[**TCP(传输控制协议)**](https://www.geeksforgeeks.org/tcp-services-and-segment-structure/) **:**
TCP 是第 4 层协议，它对收到的数据包提供确认，并且在重新发送丢失的数据包时也是可靠的。它比 UDP 好，但是由于这些特性，它有额外的开销。它被应用协议使用，如 HTTP 和 FTP。

[**UDP(用户数据报协议)**](https://www.geeksforgeeks.org/computer-network-user-datagram-protocol-udp/) **:**
UDP 也是第 4 层协议，但与 TCP 不同，它不提供对发送的数据包的确认。因此，它是不可靠的，并且依赖于更高层的协议。但另一方面，它简单、可扩展，并且与 TCP 相比开销更小。它用于视频和语音流。

**TCP Vs UDP–**

1.  **Session Multiplexing:** 
    A single host with a single IP address is able to communicate with multiple servers. While using TCP, first a connection must be established between the server and the receiver and the connection is closed when the transfer is completed. TCP also maintains reliability while the transfer is taking place. 

    另一方面，UDP 不发送接收数据包的确认。因此，不提供可靠性。

2.  **Segmentation:** 
    Information sent is first broken into smaller chunks for transmission. 

    快速以太网的最大传输单位(MTU)是 1500 字节，而 TCP 的理论值是 65495 字节。因此，数据在被发送到较低层之前必须被分成更小的块。MSS 或最大段大小应设置得足够小，以避免碎片。TCP 支持 MSS 和路径 MTU 发现，发送方和接收方可以通过它们自动确定最大传输能力。

    UDP 不支持这个；因此，它依赖于数据分段的更高层协议。

3.  **Flow Control:** 
    If sender sends data faster than what receiver can process then the receiver will drop the data and then request for a retransmission, leading to wastage of time and resources. TCP provides end-to-end flow control which is realized using a sliding window. The sliding window sends an acknowledgement from receiver’s end regarding the data that the receiver can receive at a time. 

    UDP 不实现流量控制，同样依赖于更高层的协议。

4.  **Connection Oriented:** 
    TCP is connection oriented, i.e., it creates a connection for the transmission to take place, and once the transfer is over that connection is terminated. 

    另一方面，UDP 是无连接的，就像互联网协议一样。

5.  **Reliability:** 
    TCP sends an acknowledgement when it receives a packet. It requests a retransmission in case a packet is lost. 

    UDP 同样依赖于更高层的协议。

6。**表头:**

TCP 报头的大小为 20 字节(源端口为 16 位，目的端口为 16 位，序列号为 32 位，确认号为 32 位，报头长度为 4 位)

UDP 头的大小为 8 字节(源端口 16 位，目的端口 16 位，长度 16 位，校验和 16 位)；它比 TCP 报头小得多。

UDP 和 TCP 报头都由 16 位源端口(用于标识源的端口号)字段和 16 位目的端口(用于指定提供的应用程序)字段组成。