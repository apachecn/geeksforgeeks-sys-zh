# ADSP 全模

> 原文:[https://www.geeksforgeeks.org/adsp-fullform/](https://www.geeksforgeeks.org/adsp-fullform/)

ADSP 代表**苹果对话数据流协议**，这是一种[会话层](https://www.geeksforgeeks.org/layers-of-osi-model/)协议，用于建立在各种网络设备之间交换数据的会话。它还提供了传输层的流量控制功能。它通过流量控制来保证顺序数据传输。

**功能:**

*   It provides symmetric, connection-oriented and full-duplex communication between two sockets on AppleTalk network.
*   ADSP provides a powerful interface for its clients. Clients can use the remote to open connections, send data, receive data, and finally close connections.
*   Provide attention information mechanism for customer internal control.
*   It provides a forward reset mechanism, which allows the client to stop transmitting unfinished data bytes to the remote client.
*   It also includes a built-in flow control function, which ensures that the data will be sent by the application only when its remote partner has the buffer capacity to receive the data.
*   Data can be transmitted as a continuous stream or broken down into messages by the client logic.
*   The connection may be rejected by this protocol.

**优势:**

*   Include session and transportation services.
*   Half-open connection does not exist in ADSP, that is, full-duplex protocol.
*   Ensure sequential data transmission, that is, it is a reliable protocol.
*   Duplicate data is not transmitted.
*   It uses connection control block (CCB) to set control information for synchronous communication and error checking between sockets.

**缺点:**

*   Does not include authentication and encryption functions.
*   Transmission service data unit (TSDUs) is not supported by default.