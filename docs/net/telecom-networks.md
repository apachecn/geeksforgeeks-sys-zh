# 电信网络

> 原文:[https://www.geeksforgeeks.org/telecom-networks/](https://www.geeksforgeeks.org/telecom-networks/)

电信网络目前主要用于广域通信。在每一对可能想要通信的电话之间架设一根电线不是一个好的长期策略。一个更好的主意是把所有的电话连接到一个中央交换局。在那里，接线员可以通过交换台把一部电话接到另一部电话上。

**路由电话:**
呼叫向上路由通过更高级别的交换局，直到它到达交换局，交换局可以通过与更低级别的交换局连接来到达目的地电话，交换局检查您拨打的电话号码的数字来做出这些决定。

**面向连接的服务–I:**
在整个会话期间，端点之间保持专用连接。通常，这意味着服务质量可以在所建立的信道的带宽范围内得到合理保证。消息位以发送的相同顺序到达。传统的电话电路是面向电路交换连接的系统。

**电话系统中的传输介质:**
在传统的模拟电话系统中，电话通过 3 类 UTP 电缆连接到本地交换机。这种连接称为本地循环。它的长度通常在 1 公里到 10 公里之间。在层级的更高层，更高带宽的电缆用于承载多个电话呼叫。这比使用单独的电缆进行单独的通话要便宜得多。具体来说，使用光纤上的数字线路。模拟系统使用一种称为频分复用(FDM)的技术来实现这一点。

**本地环路:**
用户手机由交易所的电池组供电。使用回声抑制器，传输是半双工的。有了回声消除器，就有可能实现全双工通信。由于本地环路仍然是模拟的，我们需要调制解调器来发送数字数据。由于一位用于控制目的，我们通常获得 56kbps 的速度。根据线路状况，调制解调器可能会自动协商较低的速度。

**信令:**
信令是指终端设备、交换机、路由器之间为建立电路、端接、计费、高级网络服务等而进行的信息交换。在频带中的公共信道信令中，帧中的一些比特用于此目的，其中 SS7 被认为是标准的。无论是**带内**还是**带外**，从逻辑上讲，交换机控制器都可以被认为是控制平面中的覆盖网络。带外信令(CCIS-公共信道局间信令)更灵活，因为它允许任意复杂的消息传输，因为它们不干扰常规信道。

**SS7 中的控制平面协议栈:**

*   **应用服务元素(ASE)–**应用级功能，例如解释信令消息。事务能力应用程序部分(TCAP)允许系统调用远程机器上的过程调用。

*   **消息传输第 1 部分(MTP-1)–**这是一种物理位传输，通常在像 E1 这样的数字线路上进行。SS7 的主要应用之一是电话用户部分(TUP)，它负责建立语音呼叫。TUP 解释拨号数字、路由、保留资源、维护帐户等。

**电话网络中的数字技术:**
在过去的 30 年里，许多传统的模拟电话网络已经被数字技术所取代。一种称为**编解码器(编码器/解码器)**的设备用于将模拟语音信号转换为数字信息，这些信息可以通过数字技术处理。编解码器还用于将数字信号转换回模拟语音信号，这些信号可以由旧的模拟技术处理。

只有本地环路仍然是模拟的，这个环路可以由**综合业务数字网络(ISDN)** 连接代替。它被设想为一种端到端的数字服务。家庭用户将通过相同的 Cat3 电缆连接。数字比特流被时分复用。系统使用带外信令，并为此使用 D 信道。 **NT1** 是一种网络终端设备，一端连接到综合业务数字网交换机，另一端连接到本地无源总线，最多可悬挂八个终端设备。甚至在标准最终确定之前，ISDN 就已经非常昂贵和过时了。宽带综合业务数字网的愿景寻求通过自动柜员机来实现。

**数字用户环路:**
下一次转换模拟本地环路的尝试有两个方向:

1.  大用户可以通过将光纤连接到他们的场所来获得服务，该场所可以终止于集成的数字插座。
2.  小用户市场是由用户对通过同一根 Cat3 电缆进行互联网连接的更大带宽需求驱动的。