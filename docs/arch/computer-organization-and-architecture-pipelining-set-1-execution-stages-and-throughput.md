# 计算机组织和架构|流水线|集合 1(执行、阶段和吞吐量)

> 原文:[https://www . geesforgeks . org/computer-organization-and-architecture-pilot-set-1-execution-stages-and-throughput/](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/)

为了提高中央处理器的性能，我们有两个选择:
1)通过引入更快的电路来改善硬件。
2)安排硬件，以便可以同时执行多个操作。

既然硬件的速度有限制，更快电路的成本也相当高，我们就不得不采用 2 <sup>和</sup>选项。

**流水线化:**流水线化是对 CPU 的硬件元件进行排列，使其整体性能提高的过程。在流水线处理器中同时执行一条以上的指令。

让我们看一个基于流水线操作概念的真实例子。考虑一个水瓶包装厂。假设一个瓶子要经过 3 个阶段，插瓶( **I** )、灌瓶( **F** )和封瓶( **S** )。让我们将这些阶段分别视为阶段 1、阶段 2 和阶段 3。让每个阶段花 1 分钟来完成它的操作。
现在，在非流水线操作中，首先将瓶子插入设备中，1 分钟后将瓶子移动到第 2 阶段，在该阶段中装满水。现在，在第一阶段，什么都没有发生。类似地，当瓶子移动到阶段 3 时，阶段 1 和阶段 2 都是空闲的。但是在流水线操作中，当瓶子处于阶段 2 时，可以在阶段 1 加载另一个瓶子。类似地，当瓶子处于阶段 3 时，阶段 1 和阶段 2 中可以各有一个瓶子。所以，每过一分钟，我们就会在第三阶段结束时得到一瓶新的。因此，制造一瓶的平均时间为:

**无流水线** = 9/3 分钟= 3m

```
I F S | | | | | |
| | | I F S | | |
| | | | | | I F S (9 minutes)

```

**带流水线** = 5/3 分钟= 1.67 米

```
I F S | |
| I F S |
| | I F S (5 minutes)

```

因此，流水线操作提高了系统的效率。

**基本管线的设计**

*   在流水线处理器中，流水线有两端，即输入端和输出端。在这些端之间，有多个级/段，使得一个级的输出连接到下一级的输入，并且每个级执行特定的操作。
*   接口寄存器用于保存两级之间的中间输出。这些接口寄存器也称为锁存器或缓冲器。
*   流水线中的所有级以及接口寄存器都由一个公共时钟控制。

**流水线处理器中的执行**
流水线处理器中指令的执行序列可以使用时空图来可视化。例如，假设一个处理器有 4 个阶段，并且有 2 条指令要执行。我们可以通过以下时空图来可视化执行序列:

**非重叠执行:**

| 阶段/周期 | one | Two | three | four | five | six | seven | eight |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| S1 | 一 <sub>1</sub> |  |  |  | 一<sub>二</sub> |  |  |  |
| S2 |  | 一 <sub>1</sub> |  |  |  | 一<sub>二</sub> |  |  |
| S3 |  |  | 一 <sub>1</sub> |  |  |  | 一<sub>二</sub> |  |
| 第四心音 |  |  |  | 一 <sub>1</sub> |  |  |  | 一<sub>二</sub> |

总时间= 8 个周期

**重叠执行:**

| 阶段/周期 | one | Two | three | four | five |
| --- | --- | --- | --- | --- | --- |
| S1 | 一 <sub>1</sub> | 一<sub>二</sub> |  |  |  |
| S2 |  | 一 <sub>1</sub> | 一<sub>二</sub> |  |  |
| S3 |  |  | 一 <sub>1</sub> | 一<sub>二</sub> |  |
| 第四心音 |  |  |  | 一 <sub>1</sub> | 一<sub>二</sub> |

总时间= 5 个周期

**管道阶段**

RISC 处理器有 5 级指令流水线来执行 RISC 指令集中的所有指令。以下是 RISC 管道的 5 个阶段及其各自的操作:

*   **阶段 1(取指令)**
    在这个阶段，中央处理器从内存中的地址读取指令，该地址的值存在于程序计数器中。
*   **阶段 2(指令解码)**
    在该阶段，指令被解码，并且寄存器文件被访问以从指令中使用的寄存器获得值。
*   **阶段 3(指令执行)**
    在该阶段，执行 ALU 操作。
*   **第 4 阶段(内存访问)**
    在该阶段，内存操作数从指令中存在的内存中读取或写入指令中存在的内存。
*   **阶段 5(写回)**
    在该阶段，计算/提取的值被写回指令中存在的寄存器。

**流水线处理器的性能**
考虑时钟周期时间为“Tp”的“k”段流水线。假设流水线处理器中有 n 个任务要完成。现在，第一条指令需要‘k’个周期才能从流水线中出来，但是其他‘n–1’条指令每个只需要‘1’个周期，即总共‘n–1’个周期。因此，在流水线处理器中执行“n”条指令所需的时间:

```
                     ETpipeline = k + n – 1 cycles
                              = (k + n – 1) Tp

```

在同样的情况下，对于非流水线处理器,“n”条指令的执行时间为:

```
                    ETnon-pipeline = n * k * Tp

```

因此，当“n”个任务在同一处理器上执行时，流水线处理器比非流水线处理器的加速比是:

```
    S = Performance of pipelined processor /
        Performance of Non-pipelined processor

```

由于处理器的性能与执行时间成反比，

```
   S = ETnon-pipeline / ETpipeline
    => S =  [n * k * Tp] / [(k + n – 1) * Tp]
       S = [n * k] / [k + n – 1]

```

当任务数“n”明显大于 k 时，即 n >> k

```
    S = n * k / n
    S = k

```

其中“k”是管道中的级数。

另外，**效率** =给定加速/最大加速= S / S <sub>最大</sub>
我们知道，Smax = k

所以，**效率** = S / k

**吞吐量** =指令数/完成指令的总时间

因此，**吞吐量**= n/(k+n–1)* Tp

注:理想流水线处理器的每指令周期值为 1

依赖关系和数据风险见 [**设置 2**](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-2-dependencies-and-data-hazard/) ，管道类型和停转见 [**设置 3**](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-3-types-and-stalling/) 。

来源:[goo.gl/J9KVNt](http://goo.gl/J9KVNt)T2[https://en . Wikipedia . org/wiki/hard _(计算机 _ 架构)](https://en.wikipedia.org/wiki/Hazard_(computer_architecture))T5】T6】https://en.wikipedia.org/wiki/Data_dependency

本文由绍拉布·夏尔马撰写。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论