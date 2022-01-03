# 8085 程序将一个十六进制数转换成 ASCII 码

> 原文:[https://www . geesforgeks . org/8085-程序-将一个十六进制数转换为 ascii 码/](https://www.geeksforgeeks.org/8085-program-to-convert-an-hexadecimal-number-into-ascii-code/)

**问题:**编写汇编级语言程序，将 HEX 代码转换为各自的 ASCII 代码。
假设程序起始地址和输入内存位置分别为 2000 和 2050。

**示例:**

```
Input: 2050 E4 (Hex data)

Output:
2051 34 (ASCII code for 4)
2052 45 (ASCII code for E) 
```

**算法:**

1.  将给定数据载入累加器，并移到 B 寄存器
2.  屏蔽累加器中六进制数的最高有效 4 位(高半字节)。
3.  调用子程序获取最低有效 4 位的 ASCII 码。
4.  将其存储在内存中
5.  将 B 寄存器移到累加器并屏蔽最低有效的 4 位(低半字节)。
6.  旋转上下半字节位置。
7.  调用子程序获取高位半字节的 ASCII 码
8.  将其存储在内存中
9.  终止程序。

**代码:**

<center>

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Two thousand | LDA 2050H | 加载十六进制数据 |
| Two thousand and three | 莫夫 b，a | 将累加器的内容移到 B |
| Two thousand and four | 阿尼奥夫 | 屏蔽上半字节 |
| Two thousand and six | 调用 SUB1 | 获取高位半字节的 ascii 码 |
| Two thousand and nine | 2051H |  |
| Two thousand and twelve | 莫夫 a b | 将内容移动到累加器 |
| Two thousand and thirteen | 阿尼 F0H | 屏蔽下半字节 |
| Two thousand and fifteen | RLC |  |
| Two thousand and sixteen | RLC |  |
| Two thousand and seventeen | RLC |  |
| Two thousand and eighteen | RLC |  |
| Two thousand and nineteen | 调用 SUB1 | 获取低位半字节的 ascii 码 |
| Two thousand and twenty-two | 2052H |  |
| Two thousand and twenty-five | HLT |  |
| SUB1 | 消费物价指数 0AH |  |
|  | JC SKIP |  |
|  | 阿迪 07H |  |
| 跳跃 | 名字是 30H |  |
|  | 浸水使柔软 |  |

</center>

**说明:**

1.  **LDA 2050H:** 将内存位置 2050H 的内容加载到累加器中。
2.  **MOV B，A:** 将累加器的内容复制到寄存器 B
3.  **ANI OFH:** 在累加器和 0FH 值之间执行“与”运算。
4.  **调用 SUB1:** 调用内存位置 SUB1 的子程序。
5.  **STA 2051H:** 将累加器的内容存储在存储单元 2051H 中。
6.  **MOV A、B:** 将寄存器 B 的内容复制到累加器。
7.  **ANI F0H:** 在累加器和 F0H 值之间进行 AND 运算。
8.  **RLC:** 向左旋转蓄能器。
9.  **HLT:** 停止执行程序并停止任何进一步的执行。
10.  **CPI 0AH:** 比较累加器含量与 0AH 值。
11.  **JC SKIP:** 如果进位位被置位，跳到存储单元 SKIP。
12.  **ADI 07H:** 将 07H 值加到累加器的内容中。
13.  **RET:** 无条件从子程序返回。