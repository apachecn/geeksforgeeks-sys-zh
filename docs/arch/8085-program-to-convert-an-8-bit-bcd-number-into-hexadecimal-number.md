# 8085 程序将一个 8 位 BCD 数转换成十六进制数

> 原文:[https://www . geesforgeks . org/8085-程序-将一个 8 位 bcd 数字转换为十六进制数字/](https://www.geeksforgeeks.org/8085-program-to-convert-an-8-bit-bcd-number-into-hexadecimal-number/)

**问题–**在 8085 微处理器中编写汇编语言程序，将一个 8 位 BCD 数转换为十六进制数。

**假设–**假设程序的起始地址为 2000，输入内存位置为 2050、2051，输出内存位置为 2052。

**示例–**

```
INPUT: 2050:02H
       2051: 09H

OUTPUT:2052: 1DH 
```

**算法–**

1.  将内存指针初始化为 2050
2.  获取最高有效数字
3.  使用重复加法将 MSD 乘以 10
4.  将 LSD 添加到上述步骤中获得的结果中
5.  将转换结果存储在存储器 2052 中

**程序–**

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Two thousand | LXI H，2050 年 |  |
| Two thousand and three | 莫夫 a，m | A |
| Two thousand and four | 添加一个 | A |
| Two thousand and five | 莫夫 b，a | B |
| Two thousand and six | 添加一个 | A |
| Two thousand and seven | 添加一个 | 一
 |
| Two thousand and eight | 添加 B | A |
| Two thousand and nine | INX H(消歧义) |  |
| 200A | 添加 M | A |
| 200B | INX H(消歧义) |  |
| 200 摄氏度 | 莫夫 m，a | M |
| 200D | HLT | 终止程序 |

**说明–**寄存器 H、L、B、A 用于通用。

1.  **LXI H，2050:** 将用存储单元的地址 2050 加载 HL 对寄存器。
2.  **MOV A，M:** 将内存内容复制到寄存器 A
3.  **ADD A:** 将累加器的内容与自身相加。
4.  **MOV B，A:** 将累加器的内容移入寄存器 B
5.  **ADD A:** 将累加器的内容与自身相加。
6.  **ADD A:** 将累加器的内容与自身相加。
7.  **ADD B:** 将累加器的内容与寄存器 B 相加，并将结果存入累加器。
8.  **INX H:** 递增寄存器对 HL。
9.  **ADD M:** 用内存添加累加器的内容，并将结果存入累加器。
10.  **INX H:** 递增寄存器对 HL。
11.  **MOV M，A:** 将累加器的内容复制到内存中。
12.  **HLT:** 停止执行程序并停止任何进一步的执行。