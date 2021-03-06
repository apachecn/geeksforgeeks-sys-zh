# TCP 中的错误控制

> 原文:[https://www.geeksforgeeks.org/error-control-in-tcp/](https://www.geeksforgeeks.org/error-control-in-tcp/)

**先决条件–**[TCP/IP 模型](https://www.geeksforgeeks.org/computer-network-tcpip-model/)
TCP 协议有找出损坏段、缺失段、无序段和重复段的方法。

**TCP 中的错误控制**主要是通过使用**三个简单的技术**来完成的:

1.  **校验和–**每个数据段都包含一个校验和字段，用于查找损坏的数据段。如果数据段损坏，则该数据段会被目标 TCP 丢弃，并被视为丢失。
2.  **确认–**TCP 还有另一种称为确认的机制，用于确认数据段已经传送。不包含数据但具有序列号的控制段也将被确认，但确认段不会被确认。
3.  **重传–**当一个数据段丢失，延迟传送到接收器，被接收器检查时损坏，然后该数据段再次重传。只有在两种情况下才会重传数据段:发送方收到三个重复确认或重传计时器超时。
    1.  **RTO 后的重传:**对于所有已发送但未确认的数据段，TCP 始终保留一个重传超时(RTO)计时器。当计时器超时时，最早的数据段将被重新传输。这里没有为确认设置计时器。在 TCP 中，RTO 值本质上是动态的，它使用数据段的往返时间(RTT)进行更新。RTT 是数据段到达接收者和发送者收到确认所需的持续时间。
    2.  **三个重复 ACK 段后重传:** RTO 方法在 RTO 值较小时效果较好。如果很大，则需要更多的时间来确认某个细分市场是否已经交付。有时会丢失一个数据段，接收方会收到太多无序的数据段，以至于无法保存。为了解决这种情况，使用了三重确认方法，并且丢失的段被立即重传，而不是重传已经传送的段。这是一种快速重传，因为它可以快速重传丢失的数据段，而不是等待计时器结束。

本文由 **Swasthik** 供稿。如果你喜欢极客博客并想投稿，你也可以用 write.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。