# 网络架构的演进

> 原文:[https://www . geeksforgeeks . org/网络架构演进/](https://www.geeksforgeeks.org/evolution-of-network-architecture/)

**电报网络**允许通过长目的地传输文本消息。它也被称为无连接服务，即在传输消息之前，源地址和目的地址之间没有预先建立连接。对于信息传输，它使用莫尔斯电码将信息表示为数字信息，并通过通信线路将其作为电脉冲传输。

电报系统也被称为**存储和转发系统**，在该系统中，接收到的第一个完整消息在每个电报站被解码，然后通过编码转发到另一个站。这也可以描述为消息交换。

**网络运行:**

*   由用户提供文本信息最初由电报员使用“MORSE CODE”编码成点和破折号的序列，然后通过传输线以长短电脉冲的形式传输。
*   操作员根据目的地地址将消息路由到目的地站，这在所有中间站继续进行，直到目的地站到达。
*   在目的站，信息由操作员进行物理解码，并转发到位置。
*   该系统的主要缺点是没有充分利用传输线的潜力，因为信息的传输速率受限于操作员键入序列的速率。
*   因此，为了提高信息技术，使用了多路复用技术，将多个运营商输入的信息多路复用在一起，并通过单个传输线传输。
*   此外，还采用了波特系统，其中单个字符表示为 5 位二进制数字，通过波特多路复用与六个运营商，传输速率达到 120bps。

**电话架构的要素:**

*   它利用数字传输系统**，如莫尔斯电码和波特系统，通过网络传输信息。**
*   ****成帧**用于指示消息的开始和结束。**
*   ****分层寻址**用于将消息路由到目的地**
*   ****应用数字信息的复用**来提高传输速率。**

****电话网络:**
电话网络使用电话设备(由亚历山大·格雷厄姆·贝尔在 1876 年从事电报工作时开发)来传输语音信号。与电话系统中的电报系统实时不同，双向语音传输被包括在内。这是一种**面向连接的服务**，最初在源和目的地之间建立连接，然后传输信息。使用**电路切换**连接用户。**

****网络运行:**
早期，为用户提供的电话服务是通过在两个终端用户之间使用单独的专用线路直接连接两个终端用户，并使用模拟传输系统将声音转换成适当的电信号，然后通过线路传输，这种传输涉及一些放大信号以保持质量的方法。**

**随着电话用户数量的增加，传输线路的数量也增加了，因此**电话交换机**被引入，服务被重新定义如下。**

**此后，电话服务包括 3 个阶段:**

*   ****设置阶段–**
    想要呼叫的用户，通过拿起电话与中心电话局建立连接。**
*   ****信息传递阶段–**
    在与电话局建立连接后，用户应指定他们希望连接的目的地电话号码，在办公室操作员建立连接后，用户与其他用户交换信息。**
*   ****Connection Release –**
    When users are done, they hang up their telephones which generate a signal that call is complete. And line is made available for other users.

    传统上，办公室的连接设置具有人的内向性，操作员过去常常进行连接，后来被自动交换机取代，自动交换机将自动做出路由决定。** 

****使用的传输机制:**
在最初的日子里，模拟系统被用于传输信息，而数字传输系统取代了模拟系统，模拟语音信号被转换成二进制流&产生的数字信号在两部电话之间传输。**

**然后，对于数字传输，“T1 载波”用于传输语音信号，这也提高了效率，在这种情况下，它可以将 24 个通道传输的语音作为一个帧传输，每个通道中有 8 位信息，并进行多路复用。**

```
1 frame = 8 bits*24 channels
 = 192 bits
1 frame = 192 bits + 1 frame member
 = 193 bits
**1 frame has 193 bits** 
```

**因此，一个 T1 载波可以传输 **8000 帧/秒****

**8000 * 193 = 1544 MB/秒是标准 T1 载波实现的数据速率。因此，在电话网络中，T1 载波是用于多路复用和传输的标准。**

****电话网络体系结构的要素:**
电话网络是面向连接的，它要求在传输信息之前建立连接。它使用**电路交换**进行端到端连接，路由决定是在那里自己做出的。**

*   ****Addressing –**
    In Telephone number system each telephone had a unique telephone number which was provided using Hierarchical addressing.

    例如**号码 416-967-1111。
    前 3 位数字(即 416)指定区号。
    后 3 位数字表示中心局的交换设施。
    最后 4 位数字指定连接用户和中心局的线路。**** 
*   ******用户到网络信令–**
    用于在用户和较近的电话局之间建立连接，其中当用户拿起电话打电话时听到拨号音，向中心局发出信号，如果连接建立，用户听到拨号音。否则，就认为电话没电了。****
*   ******网络信令系统–**
    它通过向计算机发送建立路径的信号来帮助建立两部电话之间的连接。****

******互联网:**
互联网不同于电话和电报，在电话和电报中，信息传输是在同一个网络中进行的，它为跨多个不同网络的信息传输提供了便利。****

****早期的半自动地面环境(SAGE)和 ARPANET 为发展我们之间的信息传输网络做出了重大努力，逐渐地，由于计算机时代的繁荣，互联网得到了发展，连接到不同网络的计算机之间的通信得以实现。****

****在使用计算机的最初几天，它们是昂贵的。因此，一个名为面向终端的网络允许多个终端(用户或输入设备)通过通信线路直接连接并利用来自主机的资源来共享单个主机。****

****但是终端需要与主机相邻。随着通过电话网络传输数字信息的现代设备的引入，访问位于离主机更远的终端成为可能。逐渐地，终端的数量也增长了，以提供给每个终端的单独线路通过采用诸如以下的方法被改变(修改)。****

*   ******媒体访问控制–**
    所有终端与主机共享一条公共通信线路，并使用轮询机制来访问计算机，当终端被轮询时，输入被直接传输。****
*   ******统计多路复用器/集中器–**
    它还提供了另一种方法，通过终端与连接到多路复用器的终端共享公共通信线路。其中来自终端的输入消息被封装成具有报头(终端地址)的帧，并且由终端生成的所有消息被缓冲在有序队列中的多路复用器中，并被发送到主机。****

****随着计算机变得越来越便宜，每个人都有了个人计算机，因此发展了计算机到计算机的网络，使计算机之间能够交换信息。****

****因此，通信体系结构从简单的电报网络发展到今天最先进、最可靠的计算机到计算机网络体系结构，使信息能够在世界任何地方的用户之间传输。****