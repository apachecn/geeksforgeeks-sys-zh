# 计算机器的周期数和平均操作数提取率

> 原文:[https://www . geeksforgeeks . org/计算周期数和平均操作数机器提取率/](https://www.geeksforgeeks.org/calculate-number-of-cycles-and-average-operand-fetch-rate-of-the-machine/)

在本文中，我们将了解当机器使用不同的操作数访问模式时，如何计算机器的平均操作数提取率。

**示例-1 :**
考虑使用不同操作数访问模式的假设机器，如下所示。假设内存访问消耗 3 个时钟周期，算术计算消耗 2 个时钟周期，寄存器或指令本身存在数据时消耗 0 个时钟周期，机器的平均操作数提取速率是多少？

<figure class="table">

| 操作数访问模式 | 频率百分比(概率) |
| --- | --- |
| 即时访问模式 | Twenty-five |
| 寄存器访问模式 | Twenty-eight |
| 直接访问模式 | Eighteen |
| 内存间接访问模式 | Fourteen |
| 索引访问模式 | Fifteen |

**解决方案:**
在索引寻址模式下，如果没有指定任何内容，那么我们假设“**基址被直接赋予指令，索引值被存储到索引寄存器**”。现在，如果我们查看给定的操作数访问模式以及根据给定问题执行所需的周期数，我们可以看到–

**立即访问模式**不需要参考或 0 周期。
**寄存器访问模式**需要 0 寄存器参考或 0 周期。
**直接访问模式**需要 1 个内存参考或 3 个周期。
**内存间接访问模式**需要双内存参考。
或
3*2 周期(1 记忆参考有 3 个周期，所以 2 记忆参考有 3*2 个周期)。
**索引访问模式**需要 1-reg 引用和 1-mem 引用以及 1-算术计算。
或
5 个周期(1-记忆参考有 3 个周期，1-算术计算有 2 个周期)。

<figure class="table">

| 操作数访问模式 | 频率百分比(概率) | 循环数 |
| --- | --- | --- |
| 即时访问模式 | Twenty-five | 无参考(0 周期) |
| 寄存器访问模式 | Twenty-eight | 0-寄存器参考(0 周期) |
| 直接访问模式 | Eighteen | 1 记忆参考(3 周期) |
| 内存间接访问模式 | Fourteen | 2 记忆参考(3*2 周期) |
| 索引访问模式 | Fifteen | 1-寄存器参考和 1-存储器参考以及 1-算术计算(0+3+2 周期) |

</figure>

我们可以通过取频率和周期数的乘积之和得到执行一条指令所需的总平均周期数。
执行一条指令所需的总平均周期数

```
= (0.25\times0) + (0.28\times0) + (0.18\times3) + (0.14\times6) + (0.15\times5)
= 2.13 Cycles
```

现在我们知道，完成一个周期所需的时间是

```
= 1/1GHz = 1 nanosecond
```

执行一条指令所需的平均时间

```
= 2.13 ∗ 1 = 2.13 nanosecond
```

所以= 1 条指令需要 2.13 纳秒。

需要 1 秒钟

```
= 1 / (2.13 * 10^(-9)) 
= 0.469483568 * 10^9 Instructions
= 469.483568 MIPS (Million Instructions Per Second).
In general we take operation fetch rate in MIPS.
```

**示例-2 :**
考虑使用不同操作数访问模式的假设机器，如下所示。根据指令或消费物价指数计算周期。

<figure class="table">

| 指令类型 | 频率 | 指令消耗的周期 |
| --- | --- | --- |
| 算术逻辑单元指令 | 45% | four |
| 装入指令 | 35% | three |
| 存储指令 | 10% | Two |
| 分支指令 | 10% | Two |

**解决方案:**
在计算机体系结构中，每条指令的周期是处理器性能的一个方面:程序或程序片段每条指令的平均时钟周期数。它是每个周期指令的乘法逆运算。
给出了–

```
ALU Instruction consumes 4 cycles
Load Instruction consumes 3 cycles
Store Instruction consumes 2 cycles
Branch Instruction consumes 2 cycles
```

所以，我们可以通过周期和频率的乘积得到 CPI。

```
CPI = 4*0.45 + 3*0.35 + 2*0.1 + 2*0.1 
= 3.25 Cycles/Instruction
```

</figure>

</figure>