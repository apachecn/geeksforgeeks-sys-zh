# 8085 程序将两个 16 位数字相乘

> 原文:[https://www . geesforgeks . org/8085-程序乘二 16 位数字/](https://www.geeksforgeeks.org/8085-program-to-multiply-two-16-bit-numbers/)

**问题–**在 8085 微处理器中编写汇编语言程序，将两个 16 位数字相乘。

**假设–**

*   程序起始地址:2000

*   输入存储位置:2050、2051、2052、2053

*   输出内存位置:2054、2055、2056、2057

**示例–**

```
INPUT:
       (2050H) = 04H
       (2051H) = 07H 
       (2052H) = 02H 
       (2053H) = 01H
OUTPUT:
        (2054H) = 08H
        (2055H) = 12H
        (2056H) = 07H
        (2057H) = O0H
```

结果:
因此我们相乘了两个 16 位的数字。

**算法–**

1.  加载 HL 对中的第一个数据。

2.  将 HL 对的内容移动到堆栈指针。

3.  加载 HL 对中的第二个数据，并将其移动到 DE。

4.  将 H 寄存器设为 00H，将 L 寄存器设为 00H。

5.  添加 HL 对和堆栈指针。

6.  检查进位，如果进位增加 1，则进入下一步。

7.  然后将 E 移到 A，用累加器和寄存器 d 执行或运算

8.  操作的值为零，然后存储该值，否则转到步骤 3。

**程序–**

<figure class="table">

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Two thousand | LHLD 2050 年 | 加载地址为 2050 的 H-L 对 |
| Two thousand and three | 斯波尔 | 将它保存在堆栈指针中 |
| Two thousand and four | 勒瓦尔德 2052 | 加载地址为 2052 的 H-L 对 |
| Two thousand and seven | XCHG 表示 | 交换 HL 和 DE PAIR 内容 |
| Two thousand and eight | LXI H，0000 小时 | H |
| 200B | LXI B，0000 小时 | B |
| 200E | DAD SP |   |
| 200F | JNC 2013 | 跳跃不携带 |
| Two thousand and twelve | INX B(消歧义) | 将业务连续性增加 1 |
| Two thousand and thirteen | DCX D 人 | 递减 1 |
| Two thousand and fourteen | 莫夫 a，e | A |
| Two thousand and fifteen | 现在 d | 累加器和数据寄存器的内容 |
| Two thousand and sixteen | JNZ 200E 系列 | 跳跃不为零 |
| Two thousand and nineteen | SHLD 2054 突击步枪 | L |
| 201C | 莫夫·l·c | L |
| 201D | 莫夫·h·b | B |
| 201E | SHLD 2056 突击步枪 | L |
| Two thousand and twenty-one | HLT | 终止程序 |

**说明–**寄存器 B、C、D、E、H、L 和累加器用于通用。

1.  **LHLD 2050:** 加载地址为 2050 的 HL 对。

2.  **SPHL:** 保存栈指针中 HL 的内容。

3.  **LHLD 2052:** 加载地址为 2052 的 H-L 对。

4.  **XCHG:** 用 DE 交换 HL 对的含量。

5.  **LXI H，0000H:** 使 H 为 00H，L 为 00H。

6.  **LXI B，0000H:** 使 B 为 00H，C 为 00H

7.  **DAD SP:** ADD HL 对和堆栈指针。

8.  **JNC 2013:** 如果没有进位就跳到地址 2013。

9.  **INX B:** 用 1 递增 BC 寄存器。

10.  **DCX D:** 将 DE 寄存器对递减 1。

11.  **MOV A，E:** 将寄存器 E 的内容移到累加器。

12.  **ORA D:** 或累加器和 D 寄存器的内容。

13.  **JNZ 200E:** 如果没有零，跳转到地址 200E。

14.  **SHLD 2054:** 将结果从 HL 对寄存器存储到存储器地址 2054 和 2055。

15.  **MOV L，C:** 将寄存器 C 的内容移到 L.

16.  **MOV H，B:** 将寄存器 B 的内容移到 H.

17.  **SHLD 2056:** 将结果从 HL 对寄存器存储到存储器地址 2056 和 2057。

18.  **HLT:** 终止程序。

</figure>