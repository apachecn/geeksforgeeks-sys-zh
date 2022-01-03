# 8085 程序减去两个 16 位数字有无借用

> 原文:[https://www . geesforgeks . org/8085-带或不带借位的两个 16 位数字加减程序/](https://www.geeksforgeeks.org/8085-program-to-subtract-two-16-bit-numbers-with-or-without-borrow/)

**问题–**在 8085 微处理器中编写汇编语言程序，减去两个 16 位数字。

**假设–**

*   项目起始地址:2000 年
*   输入内存位置:2050、2051、2052、2053
*   输出内存位置:2054，2055

**示例–**

```
INPUT:
       (2050H) = 19H
       (2051H) = 6AH 
       (2052H) = 15H 
       (2053H) = 5CH

OUTPUT:
        (2054H) = 04H
        (2055H) = OEH
```

结果:
因此我们减去了两个 16 位数字。

**算法–**

1.  获取 16 位数字的 L 寄存器中的 LSB 和 H 寄存器中的 MSB。
2.  用 DE 寄存器交换 HL 寄存器的内容。
3.  再次获取 16 位数字的 L 寄存器中的最低有效位和 H 寄存器中的最高有效位。
4.  用 E 寄存器的内容减去 L 寄存器的内容。
5.  用 D 寄存器的内容减去 H 寄存器的内容，借用上一步。
6.  将结果存储在内存位置。

**程序–**

<center>

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Two thousand | LHLD 2050 年 | 加载地址为 2050 的 H-L 对 |
| Two thousand and three | XCHG 表示 | 用双电子对交换双电子对 |
| Two thousand and four | 勒瓦尔德 2052 | 加载地址为 2052 的 H-L 对 |
| Two thousand and seven | MVI C， 00 | C |
| Two thousand and nine | 莫夫 a，e | A |
| 200A | SUB L | A |
| 200B | STA 2054 | 2054 |
| 200E | 莫夫 a，d | A |
| 200F | SBB H(消歧义) | 借减 |
| Two thousand and ten | STA 2055 | 2055 |
| Two thousand and thirteen | HLT | 终止程序 |

</center>

**解释–**

1.  **LHLD 2050:** 加载地址为 2050 的 HL 对。
2.  **XCHG:** 用 DE 交换 HL 对的含量。
3.  **LHLD 2052:** 加载地址为 2050 的 HL 对。
4.  **MOV A，E:** 将寄存器 E 的内容移到 A
5.  **SUB L:** 用寄存器 L 的内容减去 A 的内容。
6.  **STA 2054:** 将累加器的结果存储到内存地址 2054。
7.  **MOV A、D:** 将寄存器 D 的内容移到 A
8.  **SBB H:** 用借位寄存器 H 的内容减去 A 的内容。
9.  **STA 2055:** 将累加器的结果存储到内存地址 2055。
10.  **HLT:** 停止执行程序并停止任何进一步的执行。