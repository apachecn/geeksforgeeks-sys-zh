# 并行计算和分布式计算的区别

> 原文:[https://www . geeksforgeeks . org/并行计算和分布式计算的区别/](https://www.geeksforgeeks.org/difference-between-parallel-computing-and-distributed-computing/)

**[并行计算](https://www.geeksforgeeks.org/introduction-to-parallel-computing/) :**
在并行计算中，多个处理器同时执行分配给它们的多个任务。并行系统中的内存可以是共享的，也可以是分布式的。并行计算提供了并发性，节省了时间和金钱。

**[【分布式计算】](https://www.geeksforgeeks.org/distributed-database-system/) :**
在分布式计算中，我们有多台自主计算机，在用户看来，它们就像一个系统。在分布式系统中，没有共享内存，计算机通过消息传递相互通信。在分布式计算中，单个任务被分配给不同的计算机。

**并行计算和分布式计算的区别:**

<center>

| S.NO | 并行计算 | 分布式计算 |
| 1. | 许多操作同时进行 | 系统组件位于不同的位置 |
| 2. | 需要单台计算机 | 使用多台计算机 |
| 3. | 多个处理器执行多个操作 | 多台计算机执行多种操作 |
| 4. | 它可能有共享或分布式内存 | 它只有分布式内存 |
| 5. | 处理器通过总线相互通信 | 计算机通过信息传递相互通信。 | 6. | 提高系统性能 | 提高系统可扩展性、容错能力和资源共享能力 |

</center>