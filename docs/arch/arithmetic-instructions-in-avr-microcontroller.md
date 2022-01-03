# AVR 微控制器中的算术指令

> 原文:[https://www . geeksforgeeks . org/算术-指令 in-AVR-微控制器/](https://www.geeksforgeeks.org/arithmetic-instructions-in-avr-microcontroller/)

**算术指令**是执行加法、减法、乘法等基本算术运算的指令。AVR 微控制器有两个操作数，它们实际上是保存数据的寄存器。左寄存器是源寄存器，右寄存器是源[寄存器](https://practice.geeksforgeeks.org/problems/what-is-register)。

下表显示了**的算术指令**:

<center>

| 指令 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| 注意缺陷障碍 (Attention Deficit Disorder) | d，S | D = D+ S | 添加 D，S |
| 物理输出核心 | d，S | D = D+ S+进位 | 模数转换器 |
| 潜水艇 | d，S | D = D- S | 副驾驶员，副驾驶员 |
| 小企业委员会(Small Business Council)ˌ单板计算机(single board computer)ˌ瑞士银行公司(Swiss Bank Corp.) | d，S | D =进位 | 巴塞尔公约秘书处 |
| MUL | 我们没有签名。 | R1=结果的高位字节 |

</center>

R0=结果的低位字节

穆尔 D， S骡子！骡子签名号码R1= Higher byte of the result

R0=结果的低位字节

骡子 d，sMULSU有符号编号和无符号编号R1= Higher byte of the result

R0=结果的低位字节

马尔苏 d，s股份有限公司DD= D+1INC D数位计算设备公司(Digital Equipment Corporation)DD= D-1DEC D

**注:**这里 D 和 S 分别代表目的地和来源。
D 和 S 是语域。AVR 中没有除法指令。