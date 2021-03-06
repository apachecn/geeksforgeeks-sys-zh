# 计算机网络中的缓冲

> 原文:[https://www . geesforgeks . org/计算机网络缓冲/](https://www.geeksforgeeks.org/buffering-in-computer-network/)

**缓冲区**是一个内存区域，用于在数据从一个地方移动到另一个地方时临时保存数据。当在计算机内的进程之间移动数据时，使用缓冲区。大多数缓冲器都是用软件实现的。当接收数据的速率和处理数据的速率不同时，通常使用缓冲区。如果我们删除缓冲区，那么我们要么会丢失数据，要么会降低带宽利用率。

**什么是缓冲？**
在缓冲中，无论通信是直接的还是间接的，由通信进程交换的消息都驻留在临时队列中。

**缓冲类型:**

1.  **零容量–**
    该队列不能让任何消息在其中等待。因此它的最大长度为 0。为此，必须阻止发送进程，直到接收进程收到消息。也称为无缓冲。
2.  **有限容量–**
    这个队列有有限的长度 n，因此它可以有 n 条消息在其中等待。如果队列未满，可以将新消息放入队列，发送过程不会被阻止。它也被称为自动缓冲。
3.  **无限容量–**
    这个队列有无限长。因此，任何数量的消息都可以在其中等待。在这样的系统中，发送过程永远不会被阻塞。

**需要缓冲:**

*   它有助于两个设备之间的速度匹配，数据在这两个设备之间传输。例如，硬盘必须存储从调制解调器接收的文件。
*   它有助于不同数据传输大小的设备相互适应。
*   它帮助设备在发送或接收数据之前处理数据。
*   它还支持复制语义。