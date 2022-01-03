# SIC/XE 中使用的指令集

> 原文:[https://www . geesforgeks . org/instruction-set-use-in-sic-xe/](https://www.geeksforgeeks.org/instruction-set-used-in-sic-xe/)

先决条件–[在简化教学计算机(SIC)](https://www.geeksforgeeks.org/instruction-set-used-in-simplified-instructional-computer-sic/)
中使用的指令集由于 SIC/XE 相对于 SIC 是向上兼容的，因此 SIC 中的所有指令也在 SIC/XE 中使用。SIC/XE 独有的说明有:

<center>

| 记忆的 | 操作数 | 操作码 | 说明 |
| --- | --- | --- | --- |
| 地址 | R2 R1 | Ninety | R2 = R2 + R1 |
| 清楚的 | R1 | 04 | R1 = 0 |
| 压缩机 | R2 R1 | A0 | 比较 R1 和 R2 |
| -沙发 | R2 R1 | 9C | R2 = R2 / R1 |
| LDB | M | sixty-eight | B = M |
| LDS | M | 6C | S = M |
| 替比夫定 | M | Seventy-four | T = M |
| 骡子 | R2 R1 | Ninety-eight | R2 = R2 * R1 |
| RMO | R2 R1 | 交流电（alternating current） | R2 = R1 |
| 变化 | 北 R1 | A4 号 | R1 左移 n 次 |
| shift 键 | 北 R1 | A8 | 右移 R1 n 次 |
| 机顶盒(Set-Top-Box) | M | seventy-eight | M = B |
| 成钢 | M | 7C | M = S |
| STT | M | Eighty-four | M = T |
| SUBR | R2 R1 | Ninety-four | R2 = R2-R1 |
| TIXR | R1 | B8 | X = X+1；比较 X 和 R1 |

</center>

这里，
M 代表记忆
R1 和 R2 是寄存器(A，B，S，T)