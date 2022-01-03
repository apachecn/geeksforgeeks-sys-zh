# AEP Fullform

> 原文:[https://www.geeksforgeeks.org/aep-fullform/](https://www.geeksforgeeks.org/aep-fullform/)

AEP 代表 **AppleTalk Echo 协议**是一种传输层协议，用于测试和验证 AppleTalk 互联网的状态。该协议负责检查目的节点是否可用于开始通信会话。用来实现这个套接字的 Echoer 套接字通过这个套接字监听接收到的数据包。这个套接字检查[数据报传送协议(DDP)](https://www.geeksforgeeks.org/datagram-delivery-protocol-ddp/) 及其数据长度，以确定它是否是 AEP 数据包。当目标节点向源节点返回一个响应数据报时，可以测试它的可用性。

**功能:**

*   Echer socket(socket number 4) is used to implement the protocol in each node.
*   It measures the time of the round trip cycle.
*   It is an echo or ping type protocol.
*   Use echo function value =1 to indicate echo request, and value =2 to indicate echo response.
*   The maximum data size of AEP packet is 585 bytes.

**优势:**

*   The client can set the AEP data part of the echo request packet to any mode, and then check the data in the echo reply packet.
*   Clients can use this protocol to detect whether a node on the network is available.
*   Provide echo service for the host.
*   Provide network maintenance and connection functions.
*   Perform network performance evaluation.

**缺点:**

*   There is no application program interface (API).
*   Before the start of this agreement, the client should know the Internet address of the node that needs to respond.