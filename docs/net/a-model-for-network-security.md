# 网络安全模型

> 原文:[https://www.geeksforgeeks.org/a-model-for-network-security/](https://www.geeksforgeeks.org/a-model-for-network-security/)

当我们将数据从源端发送到目的端时，我们必须使用一些传输方法，如互联网或任何其他能够发送信息的通信渠道。交易双方是交易的主体，必须合作才能进行交易。当数据从一个源传输到另一个源时，通过定义从源到目的地的互联网路由，以及通过两个主体合作使用通信协议(例如，TCP/IP)，在它们之间建立一些逻辑信息通道。

当我们将协议用于这个逻辑信息通道时，安全性的主要方面就来了。谁可能对保密性、真实性等构成威胁。所有提供安全的技术都必须有组件:

1.  Security-related conversion of the information to be sent.
2.  Some secret information shared by the two principals, I hope the opponent doesn't know.

可能需要可信的第三方来实现安全传输。例如，第三方可能负责将秘密信息分发给双方当事人，同时不让任何对手知道。或者可能需要第三方来仲裁双方当事人之间关于消息传输真实性的争议。

该模型表明，在设计特定的安全服务时有四个基本任务:

1.  Design an algorithm to perform security-related transformation.
2.  Generate the secret information used by the algorithm.
3.  Formulate the distribution and sharing methods of secret information.
4.  Specify the protocol used by two principals, who use security algorithms and secret information to implement specific security services.