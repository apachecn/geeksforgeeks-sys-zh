# 长轮询和 WebSocket 的区别

> 原文:[https://www . geeksforgeeks . org/long-polling-and-web socket 之差/](https://www.geeksforgeeks.org/difference-between-long-polling-and-websocket/)

**1。** [**长轮询**](https://www.geeksforgeeks.org/what-are-long-polling-websockets-server-sent-events-sse-and-comet/) **:**
它是一种技术客户端，除了等待即时响应之外，还向服务器请求数据，或者本质上需要向服务器发出 HTTP 请求，然后保持连接打开，以便服务器稍后回复。在长轮询的帮助下，服务器允许来自浏览器的大约 6 个并行连接。与其他方法相比，它很方便，并且是最古老的方法，因此所有 web 浏览器都支持它。尽管由于更新较少，它现在不提供重新连接处理。

**2。**[](https://www.geeksforgeeks.org/what-are-long-polling-websockets-server-sent-events-sse-and-comet/)****:**
它是一种 pc 通信协议，允许我们通过单个传输控制协议连接实现全双工通信通道。该协议允许浏览器和网络服务器之间以低重量开销相互作用，因此提供了与服务器之间的实时数据传输。**

****长轮询与网络套接字的区别:**T2】**

| 南号码 | 长轮询 | WebSocket |
| --- | --- | --- |
| 1. | 它提供了一个单向通信通道。 | 它提供了一个双向通信通道。 |
| 2. | 存在资源浪费的问题。 | 不存在浪费资源的问题。 |
| 3. | 它的等待期很短。 | 它有很长的等待期。 |
| 4. | 它不提供资源利用。 | 它提供资源利用。 |
| 5. | 启用连接过程时不会有太多的复杂情况。 | 启用连接过程会有不同的复杂性。 |
| 6. | 在这个过程中，有几种延迟。 | 在这个过程中，没有延迟。 |
| 7. | 它使用 AJAX 进行正确的通信。 | 它不使用 AJAX 通过网络进行通信。 |