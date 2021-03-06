# 时钟驱动和事件驱动调度的区别

> 原文:[https://www . geesforgeks . org/时钟驱动和事件驱动调度的区别/](https://www.geeksforgeeks.org/difference-between-clock-driven-and-event-driven-scheduling/)

操作系统可以使用各种调度算法来调度实时任务。这些调度算法基于调度点的确定进行分类。

**1。时钟驱动调度:**
调度点由从时钟接收的中断决定的调度称为时钟驱动调度。时钟驱动调度处理下一个要处理的任务取决于时钟中断点。

**2。事件驱动调度:**
调度点由除时钟中断之外的事件事件决定的调度称为事件驱动调度。事件驱动调度处理下一个要处理的任务，与时钟中断点无关。

**时钟驱动和事件驱动调度的区别:**

<center>

| 时钟驱动调度 | 事件驱动调度 |
| --- | --- |
| 任务是根据时钟接收到的中断来安排的。 | 任务是根据除时钟中断之外的事件来安排的。 |
| 调度点由时钟中断决定。 | 调度点由任务完成和任务到达事件决定。 |
| 时钟驱动的调度算法很简单。 | 事件驱动的调度算法非常复杂。 |
| 时钟驱动的调度不如事件驱动的灵活。 | 事件驱动调度比时钟驱动更灵活。 |
| 它只能处理周期性任务。 | 它可以安排周期性的、零星的和不定期的任务。 |
| 这叫做离线调度。 | 这叫做在线调度。 |
| 它广泛应用于嵌入式系统。 | 它不太适合嵌入式系统。 |
| 它比事件驱动更有效。 | 它很复杂，但更精通。 |
| 它用于小型应用。 | 它用于较大的应用中。 |

</center>