# 点对点协议自动机事件

> 原文:[https://www . geesforgeks . org/点对点协议-ppp-automaton-events/](https://www.geeksforgeeks.org/point-to-point-protocol-ppp-automaton-events/)

选项协商自动机一般提供有限状态自动机。与大多数有限状态机一样，事件、动作和状态转换是这种有限状态自动机的各种属性。这些属性之一，即事件，通常会导致[点对点协议(PPP)](https://www.geeksforgeeks.org/ppp-full-form/) 连接从一种状态转换到另一种状态。这就是所谓的状态转换。

事件基本上是一个外部事件或任何命令，启动或触发状态机从一个状态改变到另一个状态，或保持其当前或当前状态。动作也会因事件而触发。

因此，我们可以说状态转移和动作都是由无限自动机事件引起或引发的。

共有十三个事件导致不同的购买力平价过渡状态之一。下表列出了这些事件:

<center>

| 事件 | 描述 |
| --- | --- |
| 向上 | 这个事件标签仅仅意味着下层是向上的。此事件仅在它从较低层获得准备好传输数据帧的信号时发生。该事件还向 LCP(链路控制协议)指示连接或链路将进入链路建立阶段，即通过交换数据帧或数据包来建立连接。 |
| 向下 | 这个事件标签仅仅意味着下层是向下的。只有当它从较低层获得信号，表明它现在准备好传输数据帧时，此事件才会发生。该事件还向 LCP(链路控制协议)指示连接或链路将进入链路停滞阶段，即连接或链路将终止。 |
| 打开 | 这个事件标签仅仅意味着管理开放。此事件表示允许打开连接或链接来交换数据帧。 |
| 关闭 | 这个事件标签仅仅意味着管理开放。此事件表示不允许打开连接或链接，相反，它将保持关闭状态以交换数据帧。 |
| TO+ | 此事件标签仅表示计数器大于 0 时超时。它表示重启定时器到期，重启计数器保持大于零。它将启动配置请求或终止请求数据包的重传。 |
| 到 | 这个事件标签仅仅意味着计数器超时。它表示重启定时器到期，重启计数器不再大于零。它不会启动配置请求或终止请求数据包的重传。 |
| RCR+ | 这个事件标签仅仅意味着接收配置请求是可以接受的。它表明从对等方或客户端接收到的想要打开连接的配置请求数据包是好的并且是可接受的。因此，它启动相应配置确认的传输。 |
| RCR | 这个事件标签仅仅意味着接收配置请求是不可接受的。它表示从对等方或客户端接收到的想要打开连接的配置请求数据包是不好的，是不可接受的。因此，它启动相应的配置-nak 或配置-拒绝的传输。 |
| 中非共和国 | 这个事件标签仅仅意味着接收配置确认。此事件主要发生在从客户端或对等端收到有效的肯定响应(即配置确认包到配置请求包)时。 |
| 皇家护理学院 | 这个事件标签仅仅意味着接收配置 nak/rej。此事件主要发生在从客户端或对等方收到有效的否定响应(即配置-nak 或配置-拒绝数据包到配置-请求数据包)时。 |
| RTR | 该事件标签简单地表示接收终止请求:当接收到终止请求包时，该事件发生。这个终止请求包表明对等体或客户端想要关闭或终止链路或连接。 |
| 公路交通事故 | 这个事件标签仅仅意味着接收终止确认。此事件通常发生在对等方或客户端响应终止请求数据包发送终止确认数据包时。 |
| 北爱尔兰皇家警察队 | 这个事件标签仅仅意味着接收未知代码。此事件通常发生在对等方或客户端发送不可解释的数据包时，即作为响应的代码拒绝数据包。 |
| RXJ+ | 该事件标签仅表示允许接收代码拒绝或接收协议拒绝。当对等方或客户端发送可接受的代码拒绝或协议拒绝数据包(如扩展代码的代码拒绝或 NCR 的协议拒绝)时，会发生此事件。 |
| RXJ | 该事件标签仅表示接收代码拒绝灾难性或接收协议拒绝。当对等方或客户端发送不可接受的代码拒绝或协议拒绝数据包(如配置请求的代码拒绝或 LCP 的协议拒绝)时，会发生此事件。 |
| RXR | 这个事件标签仅仅意味着接收回显请求、接收回显回复或接收丢弃请求。当对等方或客户端发送数据包(即回送请求、回送回复或丢弃请求)时，会发生此事件。 |

</center>