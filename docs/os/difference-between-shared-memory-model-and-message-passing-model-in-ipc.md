# IPC 中共享内存模型和消息传递模型的区别

> 原文:[https://www . geesforgeks . org/共享内存模型和消息传递模型在 ipc 中的区别/](https://www.geeksforgeeks.org/difference-between-shared-memory-model-and-message-passing-model-in-ipc/)

先决条件–[进程间通信](https://www.geeksforgeeks.org/inter-process-communication-ipc/)
**1。共享内存模型:**
在这个 IPC 模型中，建立了一个共享内存区域，供进程用于数据通信。这个内存区域存在于创建共享内存段的进程的地址空间中。想要与这个进程通信的进程应该将这个内存段附加到它们的地址空间中。

**2。消息传递模型:**
在这个模型中，进程通过交换消息相互通信。为此，进程之间必须存在通信链路，并且它必须促进至少两个操作发送(消息)和接收(消息)。消息的大小可以是可变的，也可以是固定的。

**IPC 中共享内存模型和消息传递模型的区别:**

<center>

| S.No | 共享内存模型 | 消息传递模型 |
| --- | --- | --- |
| 1. | 共享内存区域用于通信。 | 消息传递工具用于通信。 |
| 2. | 它用于单处理器或多处理器系统上的进程之间的通信，其中通信进程驻留在同一台机器上，因为通信进程共享一个公共地址空间。 | 它通常用在分布式环境中，通信进程驻留在通过网络连接的远程机器上。 |
| 3. | 从共享内存中读写数据的代码应该由应用程序程序员明确编写。 | 这里不需要这样的代码，因为消息传递工具提供了通信机制和由通信进程执行的动作的同步。 |
| 4. | 它提供了最大的计算速度，因为通信是通过共享内存完成的，所以系统调用只是为了建立共享内存。 | 因为消息传递是通过内核干预(系统调用)实现的，所以很耗时。 |
| 5. | 这里，进程需要确保它们不会同时写入同一个位置。 | 这对于共享少量数据很有用，因为冲突不需要解决。 |
| 6. | 更快的沟通策略。 | 相对较慢的通信策略 |

</center>