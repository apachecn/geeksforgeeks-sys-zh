# 8085 程序生成斐波那契数列

> 原文:[https://www . geesforgeks . org/8085-program-generate-Fibonacci-series/](https://www.geeksforgeeks.org/8085-program-generate-fibonacci-series/)

**问题–**在 8085 微处理器中编写汇编语言程序，生成斐波那契数列。

**示例–**假设斐波那契数列存储在起始存储位置 3050。

![6666](img/2b94f506b7ff0283389e1b7ce90605e6.png)

**注意–**这个程序生成十六进制数的斐波那契数列。

**算法–**

1.  用 30 初始化寄存器 H，用 50 初始化寄存器 L，这样间接存储器 M 指向存储单元 3050。
2.  用 00 初始化寄存器 B，用 08 初始化寄存器 C，用 01 初始化寄存器 D。
3.  在 m 中移动 B 的内容。
4.  将 M 增加 1，使 M 指向下一个存储位置。
5.  在 m 中移动 D 的内容。
6.  移动累加器 a 中的 B 的内容
7.  在 a 中加入 D 的内容。
8.  移动 b 中 D 的内容。
9.  在 d 中移动 A 的内容。
10.  将 M 增加 1，使 M 指向下一个存储位置。
11.  在 m 中移动 A 的内容。
12.  C 减 1。
13.  如果 ZF = 0，跳到存储单元 200，否则暂停程序。

**程序–**

| 存储地址 | 记忆术 | 评论 |
| <font color="black">2000</font> | <font color="black">LXI H，3050</font> | <font color="black">H < - 30，L < - 50</font> |
| <font color="black">2003</font> | <font color="black">MVI C，08</font> | <font color="black">C < - 08</font> |
| <font color="black">2005</font> | <font color="black">MVI B， 00</font> | <font color="black">B < - 00</font> |
| <font color="black">2007</font> | <font color="black">MVI D，01</font> | <font color="black">D < - 01</font> |
| <font color="black">2009</font> | <font color="black">MOV M，B</font> | <font color="black">M < - B</font> |
| <font color="black">200A</font> | <font color="black">INX H</font> | <font color="black">M < - M + 01</font> |
| <font color="black">200B</font> | <font color="black">MOV M，D</font> | <font color="black">M < - D</font> |
| <font color="black">200 摄氏度</font> | <font color="black">MOV A，B</font> | <font color="black">A < - B</font> |
| <font color="black">200D</font> | <font color="black">加 D</font> | <font color="black">A < - A + D</font> |
| <font color="black">200E</font> | <font color="black">MOV B，D</font> | <font color="black">B < - D</font> |
| <font color="black">200F</font> | <font color="black">MOV D，A</font> | <font color="black">D < - A</font> |
| <font color="black">2010</font> | <font color="black">INX H</font> | <font color="black">M < - M + 01</font> |
| <font color="black">2011</font> | <font color="black">MOV M，A</font> | <font color="black">M < - A</font> |
| <font color="black">2012</font> | <font color="black">DCR C</font> | <font color="black">C<-C–01</font> |
| <font color="black">2013</font> | <font color="black">JNZ 200C</font> | <font color="black">如果 ZF = 0 则跳转</font> |
| <font color="black">2016</font> | <font color="black">HLT</font> | <font color="black">结束</font> |

**说明–**寄存器 A、B、C、D、H、L 用于通用。

1.  **LXI H 3050:** 给 H 分配 30，给 l 分配 50。
2.  **MVI B，00:** 给 B 分配 00
3.  **MVI C，08:** 给 C 分配 08
4.  **MVI D，01:** 给 D 分配 01
5.  **MOV M，B:** 移动 M 中 B 的内容
6.  **INX H:** 将 M 增加 1。
7.  **MOV M，D:** 移动 M 中 D 的内容
8.  **MOV A，B:** 移动 A 中 B 的内容
9.  **添加 D:** 添加 D 和 a 的内容，将结果存入 a。
10.  **MOV B，D:** 移动 B 中 D 的内容
11.  **MOV D，A:** 移动 D 中 A 的内容
12.  **INX H:** 将 M 增加 1。
13.  **MOV M，A:** 移动 M 中 A 的内容
14.  **DCR C:**C 减 1。
15.  **JNZ 200C:** 如果 ZF = 0，跳转到内存位置 200C。
16.  **HLT:** 停止执行程序并停止任何进一步的执行。