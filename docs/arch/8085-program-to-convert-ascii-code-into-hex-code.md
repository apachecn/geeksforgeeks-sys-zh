# 8085 程序将 ASCII 码转换为 HEX 码

> 原文:[https://www . geesforgeks . org/8085-程序转 ascii 码转十六进制码/](https://www.geeksforgeeks.org/8085-program-to-convert-ascii-code-into-hex-code/)

**问题–**编写一个汇编级语言程序，将 ASCII 代码转换为各自的 HEX Code。

**示例:**

```
Input: 
DATA: 31H in memory location 2050
Output:
DATA: 0BH in memory location 3050 
```

假设程序的起始地址、输入存储单元和输出存储单元分别是 2000、2050 和 3050。

**算法–**

1.  在累加器中输入 2050 的内容。
2.  从累加器中减去 30H。
3.  比较蓄电池和 0AH 的含量。
4.  如果累加器的内容小于 0A，则转到步骤 6，否则转到步骤 5。
5.  从累加器中减去 07H。
6.  将累加器的内容存储到存储器位置 3050。
7.  终止程序。

**程序–**

<center>-a-a-07h-a-30-[2050]

| 地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Two thousand | LDA 2050 | A |
| Two thousand and three | SUI 30H | A | Two thousand and five | 消费物价指数 0AH |  |
| Two thousand and seven | JC 200D | 检查进位 |
| 200B | SUI 07H | A | 200D | STA 3050 | [3050] | Two thousand and ten | HLT | 停止执行 |

</center>

**解释–**

1.  **LDA 2050** 将内存位置 2050 的内容加载到累加器中。
2.  **SUI 30H** 立即从累加器中减去 30H。
3.  **CPI 0AH** 立即将 0AH 与累加器的数据进行比较。
4.  **JC 200D** 检查进位，如果是，则转到地址 200D。
5.  **SUI 07H** 立即从累加器中减去 07H。
6.  **STA 3050** 将累加器的内容存储到存储单元 3050。
7.  **HLT** 停止程序执行。