# 8085 程序查找累加器的设置位

> 原文:[https://www . geeksforgeeks . org/8085-程序查找累加器的设置位/](https://www.geeksforgeeks.org/8085-program-to-find-the-set-bit-of-accumulator/)

**问题–**累加器的所有位都是 0，只有一个位是 1。用 8085 编写汇编语言程序，确定累加器的哪个位是 1。结果应该是从 1 到 8 的十进制数，并且要求存储在寄存器 c 中。

**示例–**

```
Example 1 : Accumulator Content is 10H (Hex)

Accumulator Content -> 0 0 0 1 0 0 0 0 
Result after execution -> Register C : 5 

Example 2 : Accumulator content is 02H (Hex)

Accumulator Content -> 0 0 0 0 0 0 1 0 
Result after execution -> Register C : 2

```

**解决方案–**
问题可以通过多种方法解决。这里讨论了两种方法:

1.  不使用进位标志
2.  使用进位标志

**方法 1:不使用进位标志**

**算法–**

1.  以寄存器 C 的形式初始化一个计数器
2.  用累加器将寄存器 01 加载到与，并检查设置位
3.  和寄存器 B 中累加器的内容
4.  如果“与”运算的结果为非零，则得到最终结果
5.  如果结果为零，递增计数器 C
6.  使用无线资源控制将累加器内容右移，而不影响进位标志
7.  再次执行对下一位的搜索

**程序–**

**节目起始地址->**3000 小时

<center>

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Three thousand | LXI SP，5000 小时 | 初始化堆栈指针 |
| Three thousand and three | MVI C， 01H | C |
| Three thousand and five | MVI B， 01H | B |
| Three thousand and seven | 安娜 b | 甲配乙 |
| Three thousand and eight | jnz 3010 小时 | 零点标志复位(Z=1)时跳至位置 3010H |
| 300B | INR C 中 | C |
| 300 摄氏度 | （Ladyofthe）RoyalRedCross（英国）皇家护士红十字勋章（获得者） | 不带进位向右旋转累加器 |
| 300D | jmp 3007 小时 | 无条件跳转到位置 3007H |
| Three thousand and ten | HLT | 暂停执行 |

</center>

**解释–**

1.  **LXI SP，5000H** 用于在较高位置初始化堆栈指针，使其不与程序计数器重合
2.  **MVI C，01H** 存储计数器的值，该值将在执行结束时存储最终结果
3.  **MVI B，01H** 存储 01H 注册 B
4.  **ANA B** 用累加器的最右位对寄存器 B 的内容进行逻辑与，以检查设置位
5.  **如果“与”运算得到非零值，JNZ 3010H** 跳转到“暂停”指令；这意味着该位被置位并获得最终结果
6.  **INR C** 如果“与”运算导致零值，则递增位计数器；这意味着需要继续搜索设置位
7.  **RRC** 用于在不影响进位标志的情况下右移累加器
8.  **JMP 3007H** 无条件跳转检查累加器的下一位
9.  **HLT** 暂停程序流的执行

**方法二:使用进位标志**

**算法–**

1.  以寄存器 C 的形式初始化一个计数器
2.  累加器内容通过进位标志右移
3.  计数器递增
4.  如果进位标志(累加器的最右位)被置位，则获得最终结果
5.  如果进位标志复位(CY=0)，下一位继续迭代

**程序–**

**节目起始地址->**3000 小时

<center>

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Three thousand | LXI SP，5000 小时 | 初始化堆栈指针 |
| Three thousand and three | MVI C， 00H | C |
| Three thousand and five | RAR | 通过进位向右旋转累加器 |
| Three thousand and six | INR C 中 | C |
| Three thousand and seven | jnc 3005 小时 | 如果 CY=0，跳转到位置 3005H |
| 300A | HLT | 暂停执行 |

</center>

**解释–**

1.  **LXI SP，5000H** 用于在较高位置初始化堆栈指针，使其不与程序计数器重合
2.  **MVI C，00H** 存储将在执行结束时存储最终结果的计数器值
3.  **RAR** 通过进位标志将累加器向右旋转，使得在指令后进位标志包含累加器的最右位
4.  **INR C** 递增计数器
5.  **JNC 3005H** 如果没有设置进位标志，则跳转到位置 3005H，即累加器的最右位为 0。如果设置了进位标志，它不会执行
6.  **HLT** 暂停程序流的执行