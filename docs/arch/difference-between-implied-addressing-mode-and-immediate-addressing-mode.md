# 隐含寻址模式和立即寻址模式的区别

> 原文:[https://www . geesforgeks . org/隐含寻址模式和立即寻址模式的区别/](https://www.geeksforgeeks.org/difference-between-implied-addressing-mode-and-immediate-addressing-mode/)

先决条件–[寻址模式](https://www.geeksforgeeks.org/addressing-modes/)
**1。隐含寻址模式:**
在隐含寻址模式下，操作数在指令定义中隐含指定。所有引用使用累加器的寄存器的指令都是隐含模式指令。堆栈式计算机中的零地址指令也是隐含模式指令。因此，它也被称为堆栈寻址模式。

**2。立即寻址模式:**
在立即寻址模式下，操作数在指令本身中指定。在这种模式下，操作数字段包含要与指令中指定的操作结合使用的实际操作数。

**隐含寻址模式和即时寻址模式的区别:**

<figure class="table">

| 没有。 | 隐含寻址模式 | 立即寻址模式 |
| --- | --- | --- |
| 1. | 在隐含寻址模式下，指令中没有指定操作数。 | 在立即寻址模式下，操作数在指令本身中指定。 |
| 2. | 基本上，操作数是在指令定义中隐式指定的。 | 这里，操作数包含在操作数字段中，而不是地址字段中。 |
| 3. | 这种模式可用于所有寄存器参考指令。 | 这种模式对于将寄存器初始化为恒定值非常有用。 |
| 4. | 它需要 8 位或 16 位长的数据，是指令的一部分。 | 它需要比地址更多的位。 |
| 5. | 不需要获取操作数。 | 获取操作数很快。 |
| 6. | 堆栈式计算机中的零地址指令是隐含模式指令。 | 指令的地址字段可以指定存储器字或处理器寄存器。 |
| 7. | 示例:补码累加器 | 例如:MVI A 45 |

</figure>