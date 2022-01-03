# 8085 程序划分两个 16 位数字

> 原文:[https://www . geeksforgeeks . org/8085-二分频 16 位数字程序/](https://www.geeksforgeeks.org/8085-program-to-divide-two-16-bit-numbers/)

**问题–**在 8085 微处理器中编写汇编语言程序，对两个 16 位数字进行除法运算。

**假设–**

*   程序起始地址:2000

*   输入存储位置:2050、2051、2052、2053

*   输出内存位置:2054、2055、2056、2057。

**示例–**

```
INPUT:
       (2050H) = 04H
       (2051H) = 00H 
       (2052H) = 02H 
       (2053H) = 00H
OUTPUT:
        (2054H) = 02H
        (2055H) = 00H
        (2056H) = FEH
        (2057H) = FFH 
```

结果:
因此我们划分了两个 16 位数字。

**算法–**

1.  将寄存器 BC 初始化为商的 0000H。

2.  载入 HL 对中的除数，保存在 DE 寄存器对中。

3.  将红利装入 HL 对。

4.  用 E 寄存器减去累加器的内容。

5.  将内容 A 移动到 C，将内容 H 移动到 A

6.  用 d 减去借 A 的内容

7.  将累加器的值移动到 h

8.  如果 CY=1，转到步骤 10，否则转到下一步。

9.  递增寄存器 B 并跳至步骤 4。

10.  添加 DE 和 HL 的内容。

11.  将剩余部分存储在内存中。

12.  将 C 到 L & B 的内容移到 h

13.  将商存储在内存中。

**程序–**

<figure class="table">

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| Two thousand | LXI B，0000 小时 | 将商初始化为 0000 小时 |
| Two thousand and three | lhld 2052 小时 | 在 h1 中加载除数 |
| Two thousand and six | XCHG 表示 | HL 和 DE 交易所 |
| Two thousand and seven | LHLD 2050 年 | 加载红利 |
| 200A | 莫夫 a，l | 阿 |
| 200B | SUB E | A |
| 200 摄氏度 | 莫夫·l·a | 洛杉矶 |
| 200D | 莫夫 a，h | A |
| 200E | SBB D(消歧义) | A-D |
| 200F | 莫夫·h·a | H |
| Two thousand and ten | JC 2017 | 进位时跳跃 |
| Two thousand and thirteen | INX B(消歧义) | B |
| Two thousand and fourteen | JMP 200B |   |
| Two thousand and seventeen | 爸爸 D | HL |
| Two thousand and eighteen | SHLD 2056 突击步枪 | HL 存储在存储器中 |
| 201B | 莫夫·l·c | L |
| 201C | 莫夫·h·b | H |
| 201D | SHLD 2054 突击步枪 | HL 存储在存储器中 |
| Two thousand and twenty | HLT | 终止程序 |

**解释–**

1.  **LXI B，0000H:** 将 BC 寄存器初始化为 0000H。

2.  **LHLD 2052H:** 加载地址为 2052 的 HL 对。

3.  **XCHG:** 用 DE 对寄存器交换 HL 对的内容。

4.  **LHLD 2050:** 加载地址为 2050 的 HL 对。

5.  **MOV A，L:** 将寄存器 L 的内容移入寄存器 A。

6.  **SUB E:** 用累加器的内容减去寄存器 E 的内容。

7.  **MOV L，A:** 将寄存器 A 的内容移入寄存器 L。

8.  **MOV A，H:** 将寄存器 H 的内容移入寄存器 A。

9.  **SBB D:** 用带进位的累加器的内容减去寄存器 D 的内容。

10.  **MOV H，A:** 将寄存器 A 的内容移入寄存器 H。

11.  **JC 2017:** 有进位跳转到地址 2017。

12.  **INX B:** 将 BC 寄存器递增 1。

13.  **JMP 200B:** 跳转到地址 200B。

14.  **DAD D:** 添加 DE 和 HL 对的内容。

15.  **SHLD 2056:** 将 HL 对的内容存储到内存地址 2056 和 2057 中。

16.  **MOV L，C:** 将寄存器 C 的内容移入寄存器 L。

17.  **MOV H，B:** 将寄存器 B 的内容移入寄存器 H。

18.  **SHLD 2054:** 将 HL 对的内容存储到内存地址 2054 和 2055 中。

19.  **HLT:** 终止程序的执行。

</figure>