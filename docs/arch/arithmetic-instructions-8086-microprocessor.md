# 8086 微处理器中的算术指令

> 原文:[https://www . geesforgeks . org/算术-指令-8086-微处理器/](https://www.geeksforgeeks.org/arithmetic-instructions-8086-microprocessor/)

算术指令是执行基本算术运算的指令，如加法、减法等。与 8085 微处理器不同，8086 微处理器的目标操作数不必是累加器。

下表显示了算术指令列表:

| 操作码 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| 注意缺陷障碍 (Attention Deficit Disorder) | d，S | D = D + S | 添加 AX，[2050] |
| 物理输出核心 | d，S | D = D + S +预测。随身携带 | ADC AX，BX |
| 潜水艇 | d，S | D = D–S | sub ax 是] |
| 双耳同时冷热试验 | d，S | d = d–s–预测。随身携带 | SBB[2050]0050 号 |
| MUL | 8 位寄存器 | AX = AL * 8 位 reg。 | 穆尔 BH |
| MUL | 16 位寄存器 | DX AX = AX * 16 位 reg。 | 我有客户体验 |
| 断续器 | 8 或 16 位寄存器 | 执行带符号乘法 | 断续器 |
| 差异 | 8 位寄存器 | AX = AX / 8 位寄存器。；AL =商；AH =余数 | div 足球俱乐部 |
| 差异 | 16 位寄存器 | DX AX / 16 位寄存器。；AX =商；DX =余数 | CX 系列 DIV |
| 他是个白痴 | 8 或 16 位寄存器 | 执行带符号除法 | 伊迪夫·bl |
| 股份有限公司 | D | D = D + 1 | INC AX |
| 数位计算设备公司(Digital Equipment Corporation) | D | D = D–1 | DEC [2050] |
| 化学生物战(Chemical and Biological Warfare) | 没有人 | 将有符号字节转换为单词 | 化学生物战(Chemical and Biological Warfare) |
| CWD | 没有人 | 将有符号字节转换为双字 | CWD |
| 底片 | D | D = 2 对 D 的赞美 | 否定 AL |
| DAA | 没有人 | 十进制调整累加器 | DAA |
| 这是什么 | 没有人 | 减法后十进制调整累加器 | 这是什么 |
| 美国汽车协会 | 没有人 | 添加后调整累加器 | 美国汽车协会 |
| 美国科学院（American Academy of Sciences 的缩写） | 没有人 | 减法后调整累加器 | 美国科学院（American Academy of Sciences 的缩写） |
| 空对空导弹 | 没有人 | 乘法后调整累加器 | 空对空导弹 |
| 模拟式音乐母盘 | 没有人 | 除法后调整累加器 | 模拟式音乐母盘 |

这里 D 代表目的地，S 代表来源。
D 和 S 可以是寄存器、数据或内存地址。