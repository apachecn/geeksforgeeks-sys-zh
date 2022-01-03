# COM 和 DCOM 的区别

> 原文:[https://www . geesforgeks . org/difference-com-and-DCOM/](https://www.geeksforgeeks.org/difference-between-com-and-dcom/)

**1。** [**组件对象模型(COM)**](https://www.geeksforgeeks.org/life-cycle-of-component-object-model-com-object/) **:**
组件对象模型是微软在 1993 年推出的。它是为软件组件设计的接口标准。无论使用哪种编程语言，它都有助于进程间通信。COM 被称为一种软件架构，它允许从不同的软件供应商那里构建系统。它也被称为一组有助于创建动态对象的二进制标准。COM 也可以称为组件之间有效通信的标准。

使用 COM 的好处是它可以与任何能够创建对象和指针的编程语言一起使用。

**2。** [**【分布式组件对象模型(DCOM)**](https://www.geeksforgeeks.org/distributed-component-object-model-dcom/) **:**
分布式组件对象模型是专门为分布式应用而设计的。在 DCOM 被称为“网络 OLE”之前。用组件设计的应用程序不能满足分布式计算的需要，结果 DCOM 出现了。这支持了组件需要跨联网支持的计算机进行通信的需求。

使用的好处是它提供了分布式计算，它有一个分布式垃圾收集器，提高了中央处理器的利用率。

**COM 和 DCOM 的区别:**

<figure class="table">

| 的基础 | 计算机输出缩微胶片 | DCOM |
| --- | --- | --- |
| 缩写 | 组件对象模型。 | 分布式组件对象模型。 |
| 执行时间 | 客户端环境。 | 服务器环境。 |
| 装置 | 在使用它的机器上是必需的。 | 同一网络上需要。 |
| 模型类型 | COM 是一个接口标准。 | DCOM 是一个为分布式应用设计的模型。 |
| 对象可重用性 | 它允许。 | 它不允许。 |
| 允许分布式 | 不，分布式对象的这种能力。 | 是的，它能够分布对象。 |
| 内存利用率 | 它不能提供更好的利用率。 | 它有分布式对象收集器，提高了内存利用率。 |

</figure>