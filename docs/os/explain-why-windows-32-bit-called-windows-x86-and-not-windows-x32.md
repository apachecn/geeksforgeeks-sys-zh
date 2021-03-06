# 解释为什么 Windows 32 位叫 Windows x86 而不是 Windows x32

> 原文:[https://www . geesforgeks . org/explain-why-windows-32-bit-called-windows-x86-and-not-windows-x32/](https://www.geeksforgeeks.org/explain-why-windows-32-bit-called-windows-x86-and-not-windows-x32/)

在深入之前，

**我们先来快速定义一下位:**
在二进制中，位是单个字符，可以是 1 也可以是 0。我们最多可以用两位来表示四个值，其中三位最多可以表示八个值。我们可以用二进制表示的不同值的数量随着我们添加的每一位呈指数增长。
现在，我们将了解 32 位和 64 位的含义
您的计算机的整体性能和它可以运行的软件都受到它所使用的处理器的影响。

**什么是处理器？**

> 对操作计算机的基本指令做出反应并进行处理的逻辑电路称为处理器。

从 20 世纪 90 年代到 21 世纪初，大多数计算机都有一个 32 位系统，可以访问 2^32 的随机存取存储器。另一方面， *64 位处理器可以容纳 2^64* (或 18，446，744，073，709，551，616)字节的 RAM。

换句话说，一个 64 位的中央处理器可以处理比 40 亿个 32 位处理器加起来还要多的数据。因此，64 位版本的 Windows 在处理大量随机存取存储器(RAM)方面优于 32 位系统。64 位 CPU 的处理能力大于 32 位 CPU。

**现在进入正题。**

> *在技术术语中，x86 和 x64 指的是一个处理器家族以及它们都使用的指令集。它没有特别提到数据大小。*

术语 x86 是指任何源自英特尔 8086 处理器指令集的指令集。英特尔 8086 微处理器是英特尔 8085 微处理器的改进版本，于 1976 年推出。这是一个 16 位微处理器，有 20 条地址线和 16 条数据线，它包含一个复杂的指令集。它有两种操作模式，即最大和最小。最大模式适用于有几个处理器的系统，而最小模式适用于只有一个处理器的系统。

它的后继版本 80186、80286、80386 和 80486 都与原来的 8086 兼容，可以运行为其编写的代码。*最初写为 80×86，以反映芯片型号中心的改变值，但在该行的某个地方，80 被省略，只剩下 x86。*

x86 最初是 16 位处理器(8086 和 8088)的 16 位指令集，后来扩展为 32 位处理器(80386 和 80486)的 32 位指令集。但是术语 x86 已经与所有使用指令集家族的处理器保持一致。

利用英特尔 x86 指令集的较新的 CPU 仍然被称为 x86、i386 或 i686 兼容(这意味着它们都使用原始 8086 指令集的扩展)。

x64 是这种情况下的异类。x86-64 是 x86 集的 64 位扩展的原始术语。后来改名为 AMD64(因为 AMD 是最初提出 64 位扩展的公司)。64 位指令集由英特尔授权，其版本名为 EM64T。

*x86 既指指令集，也指使用指令集的处理器。*