# 流水线与非流水线

> 原文:[https://www.geeksforgeeks.org/pipelining-vs-non-pipelining/](https://www.geeksforgeeks.org/pipelining-vs-non-pipelining/)

**什么是流水线**
[**流水线**](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/) 是通过流水线或数据流水线积累来自处理器的指令。流水线是一组串联排列的数据处理单元，这样一个元素的输出就是后续元素的输入。流水线是一种在执行过程中多条指令重叠的技术。它主要用于在处理器中创建和组织指令，以便进程以并发方式运行。基本上，流水线是一个通过移除已完成的任务来频繁管理新任务添加的过程。

**流水线和非流水线的区别:**

<figure class="table">

| 流水线系统 | 非流水线系统 |
| --- | --- |
| 在流水线系统中，多条指令在执行过程中是重叠的。 | 在非流水线系统中，像解码、提取、执行和写入内存这样的过程被合并到一个单元或一个步骤中。 |
| 许多指令同时执行 | 一次只执行一条指令 |
| 流水线系统的效率取决于中央处理器调度器的效率。 | 在非流水线系统中，当一个执行单元发出一个信号表明它是空闲的时，中央处理器调度程序从等待指令池中选择指令。效率不依赖于 CPU 调度程序。 |
| 执行时间相对较少，执行周期也较少 | 相对而言，执行需要更多的时间或更多的周期数 |

</figure>