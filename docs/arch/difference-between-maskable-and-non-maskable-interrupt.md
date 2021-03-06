# 可屏蔽中断和不可屏蔽中断的区别

> 原文:[https://www . geeksforgeeks . org/可屏蔽中断和不可屏蔽中断的区别/](https://www.geeksforgeeks.org/difference-between-maskable-and-non-maskable-interrupt/)

[中断](https://www.geeksforgeeks.org/interrupts-8085-microprocessor/)是由中央处理器以外的组件引起的事件。它表示需要立即注意的外部事件的中央处理器。中断异步发生。可屏蔽中断和不可屏蔽中断是两种类型的中断。

**1。可屏蔽中断:**
可被中央处理器指令禁用或忽略的中断称为可屏蔽中断。中断可以是边沿触发、电平触发或电平触发。

```
Eg: 
RST6.5,RST7.5,RST5.5 of 8085 
```

**2。不可屏蔽中断:**
不能被中央处理器指令禁用或忽略的中断称为不可屏蔽中断。当响应时间至关重要或在正常系统操作期间不应禁用中断时，通常使用不可屏蔽中断。这种用途包括报告不可恢复的硬件错误、系统调试、剖析和处理系统重置等物种情况。

```
Eg:
Trap of 8085 
```

**可屏蔽中断和不可屏蔽中断的区别:**

<center>

| 不，先生。 | 可屏蔽中断 | 不可屏蔽中断 |
| --- | --- | --- |
| one | 可屏蔽中断是一种硬件中断，可被中央处理器的指令禁用或忽略。 | 不可屏蔽中断是指不能被中央处理器指令禁用或忽略的硬件中断。 |
| Two | 当可屏蔽中断发生时，可以在执行当前指令后进行处理。 | 当不可屏蔽中断发生时，当前指令和状态存储在堆栈中，供中央处理器处理中断。 |
| three | 可屏蔽中断有助于处理优先级较低的任务。 | 不可屏蔽中断有助于处理更高优先级的任务，如看门狗定时器。 |
| four | 用于与外围设备接口的可屏蔽中断。 | 不可屏蔽中断，用于紧急情况，如电源故障、烟雾探测器等。 |
| five | 在可屏蔽中断中，响应时间很长。 | 在不可屏蔽的中断中，响应时间很短。 |
| six | 它可以是矢量的或非矢量的。 | 所有都是矢量中断。 |
| seven | 操作可以被屏蔽或挂起。 | 操作不能被屏蔽或挂起。 |
| eight | 8085 的 RST6.5、RST7.5 和 RST5.5 是一些常见的可屏蔽中断的例子。 | 8085 微处理器的陷阱是不可屏蔽中断的一个例子。 |

</center>