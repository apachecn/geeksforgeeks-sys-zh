# 复位累加器(8085 & 8086 微处理器)

> 原文:[https://www . geesforgeks . org/reset-累加器-8085-8086-微处理器/](https://www.geeksforgeeks.org/reset-accumulator-8085-8086-microprocessor/)

**1。问题–**编写重置累加器的 8085 指令。

**解决方案–**8085 中有 4 条指令复位累加器。这些说明是:

<center>

| 没有。 | 记忆术 | 评论 |
| --- | --- | --- |
| one | MVI A， 00 | A |
| Two | ANI 00 | a 与 00 |
| three | xra a | 异或运算 |
| four | SUB A | 一 |

</center>

**解释–**

1.  **MVI A，00:** 指令副本 00 至 A
2.  **ANI 00:** 指令执行源操作数(即 00)到目的操作数(即累加器 A)的逐位 AND 运算，并将结果存储在累加器 A 中
3.  **XRA A:** 指令在源操作数和目的操作数之间执行异或运算，并将结果存储在累加器中。这里，源操作数和目的操作数都是相同的，即 a。因此，在累加器中存储的执行异或运算后的结果是 00。
4.  **SUB A:** 运算从累加器的内容中减去源操作数的内容(这里，源寄存器为 A)，并将结果存储在累加器本身。因为，源操作数和目标操作数是相同的。因此，累加器 A = 00。

**2。问题–**编写 8086 指令，用于复位累加器。

**解决方案–**8086 中有 4 条指令复位累加器。这些说明是:

<center>

| 没有。 | 记忆术 | 评论 |
| --- | --- | --- |
| one | MOV AX，0000 | AX |
| Two | 和 AX，0000 | AX |
| three | xor AX，ax | ax |
| four | SUB AX，AX | ax |

</center>

**解释–**使用寄存器 AX。

1.  **MOV AX，0000:** 复制 0000 到 AX。
2.  **AND AX，0000:** 操作逐位执行，将源操作数(0000)转换为目标操作数，并将结果存储在 AX 中。
3.  **异或 AX，AX:** 对源寄存器和目的寄存器的值进行异或运算，并将结果存储在 AX 中。源操作数和目标操作数是相同的。因此，AX = 0。
4.  **SUB AX，AX:** 运算从目的操作数的值中减去源操作数的值，并将结果存储在 AX 中。这里，两个操作数是相同的。因此，AX = 0。