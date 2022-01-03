# 8085 微处理器中的算术指令

> 原文:[https://www . geesforgeks . org/算术-指令-8085-微处理器/](https://www.geeksforgeeks.org/arithmetic-instructions-8085-microprocessor/)

算术指令是执行基本算术运算的指令，如加法、减法等。在 8085 微处理器中，目标操作数通常是累加器。在 8085 微处理器中，目标操作数通常是累加器。

下表显示了算术指令列表:

| 操作码 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| 注意缺陷障碍 (Attention Deficit Disorder) | 稀有 | A = A + R | 添加 B |
| 注意缺陷障碍 (Attention Deficit Disorder) | M | A = A + Mc | ADD 2050 |
| ADI | 8 位数据 | A = A + 8 位数据 | ADI 50 |
| 物理输出核心 | 稀有 | A = A + R + prev。携带 | 模数转换器 |
| 物理输出核心 | M | A = A + Mc + prev。携带 | ADC 2050 |
| anticlonusindex 抗痉挛的指数 | 8 位数据 | A = A + 8 位数据+ prev。携带 | ACI 50 |
| 潜水艇 | 稀有 | A = A–R | SUB B |
| 潜水艇 | M | A = A–Mc | SUB 2050 |
| 苏 | 8 位数据 | A = A–8 位数据 | SUI 50 |
| 双耳同时冷热试验 | 稀有 | A = A–R–prev。携带 | SBB B(消歧义) |
| 双耳同时冷热试验 | M | A = A–Mc-prev。携带 | SBB 2050 |
| 印度国家银行 | 8 位数据 | A = A–8 位数据–prev。携带 | SBI 50 |
| 印度卢比 | 稀有 | R = R + 1 | INR B |
| 印度卢比 | M | M = Mc + 1 | 2050 年印度卢比 |
| INX | 公关 | r.p. = r.p. + 1 | INX H(消歧义) |
| DCR | 稀有 | R = R–1 | DCR B |
| DCR | M | m = Mc–1 | DCR 2050 |
| DCX | 公关 | r . p . = r . p .–1 | DCX 小时数 |
| 爸爸 | 公关 | HL = HL + r.p . | 爸爸 H |

在表中，
R 代表寄存器
M 代表内存
Mc 代表内存内容
r.p 代表寄存器对