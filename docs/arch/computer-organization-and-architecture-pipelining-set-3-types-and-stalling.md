# 计算机组织与架构|流水线|集合 3(类型和停顿)

> 原文:[https://www . geesforgeks . org/computer-organization-and-architecture-pilot-set-3-type-and-stalling/](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-3-types-and-stalling/)

关于执行、阶段和性能(吞吐量)，请参见 [**设置 1**](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/) ，关于依赖性和数据危害，请参见 [**设置 2**](https://www.geeksforgeeks.org/computer-organization-and-architecture-pipelining-set-2-dependencies-and-data-hazard/) 。

**管道类型**

*   Uniform delay pipeline
    In this type of pipeline, all the stages will take same time to complete an operation.
    In uniform delay pipeline, **Cycle Time (Tp) = Stage Delay**

    如果级间包含缓冲器，则**周期时间(Tp) =级延迟+缓冲器延迟**

*   非均匀延迟流水线
    在这种类型的流水线中，不同的阶段需要不同的时间来完成一个操作。
    在这种类型的管道中，周期时间(Tp) =最大值(阶段延迟)

例如，如果有 4 个延迟级，1 ns、2 ns、3 ns 和 4 ns，那么

Tp =最大值(1 ns，2 ns，3 ns，4 ns) = 4 ns

如果级间包括缓冲器，

Tp =最大值(级延迟+缓冲延迟)

**示例:**考虑具有阶段延迟(2 ns、8 ns、3 ns、10 ns)的 4 段流水线。找出在上述管道中执行 100 个任务所花费的时间。
**解决方案:**由于上述管道为非线性管道，
Tp = max(2，8，3，10) = 10 ns
我们知道 ET <sub>管道</sub>=(k+n–1)Tp =(4+100–1)10 ns = 1030 ns

注:最大传输速率=每秒百万条指令

**带失速的管道性能**

```
Speed Up (S) = Performancepipeline / Performancenon-pipeline
=> S = Average Execution Timenon-pipeline / Average Execution Timepipeline
=> S = CPInon-pipeline * Cycle Timenon-pipeline / CPIpipeline * Cycle Timepipeline
```

流水线处理器的理想 CPI 为“1”。但是由于失速，它变得大于‘1’。
= >

```
S = CPInon-pipeline * Cycle Timenon-pipeline  / (1 + Number of stalls per Instruction) * Cycle Timepipeline

As Cycle Timenon-pipeline =   Cycle Timepipeline,

Speed Up (S) = CPI<sub>non-pipeline</sub> / (1 + Number of stalls per instruction) 
```

来源:[goo.gl/J9KVNt](http://goo.gl/J9KVNt)
T4【https://en . Wikipedia . org/wiki/hard _(computer _ architecture)
[https://en.wikipedia.org/wiki/Data_dependency](https://en.wikipedia.org/wiki/Data_dependency)

本文由 Saurabh Sharma 供稿。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论