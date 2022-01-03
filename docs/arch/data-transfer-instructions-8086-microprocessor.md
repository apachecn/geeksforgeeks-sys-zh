# 8086 微处理器中的数据传输指令

> 原文:[https://www . geesforgeks . org/data-transfer-instructions-8086-微处理器/](https://www.geeksforgeeks.org/data-transfer-instructions-8086-microprocessor/)

数据传输指令是在微处理器中传输数据的指令。它们也被称为复制指令。

下表显示了数据传输指令列表:

<figure class="table">

| 操作码 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| MOV | d，S | D = S | mov ax 是] |
| 推 | D | 将 D 推到堆栈中 | 推动 DX |
| 购买凭证（proof of purchase） | D | 弹出堆栈到 D | 持久性有机污染物 |
| PUSHA | 没有人 | 将所有寄存器放入堆栈 | PUSHA |
| POPA | 没有人 | 从堆栈中获取所有寄存器的字 | POPA |
| XCHG 表示 | d，S | 交换数据和文件的内容 | XCHG [2050]，AX |
| 在…里 | d，S | 将一个字节或字从 S 复制到 D | 在 AX、DX |
| 在外 | d，S | 将一个字节或字从 D 复制到 S | 输出 05，人工智能 |
| XLAT(数据中心) | 没有人 | 使用内存中的表翻译 a1 中的一个字节 | XLAT(数据中心) |
| 拉合夫 | 没有人 | 用标志寄存器的低位字节加载 AH | 拉合夫 |
| SAHF | 没有人 | 将 AH 寄存器存储到标志寄存器的低位字节 | SAHF |
| PUSHF | 没有人 | 复制堆栈顶部的标志寄存器 | PUSHF |
| 波夫 | 没有人 | 将堆栈顶部的一个字复制到标志寄存器 | 波夫 |

这里 D 代表目的地，S 代表来源。
D 和 S 可以是寄存器、数据或内存地址。

</figure>