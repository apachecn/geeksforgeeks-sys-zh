# CSMA/CA 和 CSMA/CD 的区别

> 原文:[https://www . geesforgeks . org/difference-csma-ca-and-csma-CD/](https://www.geeksforgeeks.org/difference-between-csma-ca-and-csma-cd/)

先决条件–[载波侦听多路访问(CSMA)](https://www.geeksforgeeks.org/carrier-sense-multiple-access-csma/)

[**CSMA/CD**](https://www.geeksforgeeks.org/collision-detection-csmacd/)**:**
CSMA/CD 代表**载波侦听多路访问/冲突检测**是载波传输的网络协议。它在媒体访问控制层运行。它感知到共享频道正忙于广播，并中断广播，直到该频道空闲。在 CSMA，通过其他电台的广播检测来检测 CD/CD 冲突。当在 CSMA/光盘中检测到冲突时，传输停止，站发送阻塞信号，然后站在重传之前等待随机时间上下文。

**CSMA/CA:**
CSMA/CA 代表**载波侦听多路访问/冲突避免**是载波传输的网络协议。像 CSMA/光盘一样，它也在媒体访问控制层运行。与 CSMA /光盘不同(在碰撞后有效)，CSMA/加拿大在碰撞前有效。

让我们看看 CSMA/CA 和 CSMA/CD 的区别:-

<figure class="table">

| S.NO | CSMA/CD | csma/AC |
| --- | --- | --- |
| 1. | CSMA /光盘在碰撞后有效。 | 而 CSMA /加州在碰撞前是有效的。 |
| 2. | CSMA /光盘用于有线网络。 | 而 CSMA /认证中心通常用于无线网络。 |
| 3. | 它只会减少恢复时间。 | 而 CSMA/加州将碰撞的可能性降至最低。 |
| 4. | 每当发生冲突时，CSMA /光盘会重新发送数据帧。 | 而 CSMA /认证中心将首先传输发送数据传输的意图。 |
| 5. | CSMA /光盘用于 802.3 标准。 | 而 802.11 标准使用的是 CSMA / CA。 |
| 6. | 它比简单的 CSMA(载波侦听多路访问)更有效。 | 虽然它类似于简单的 CSMA(载波侦听多路访问)。 |

</figure>