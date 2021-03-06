# AVR 微控制器中的逻辑指令

> 原文:[https://www . geesforgeks . org/logic-in-instructions-AVR-microcontroller/](https://www.geeksforgeeks.org/logical-instructions-in-avr-microcontroller/)

逻辑指令是执行基本算术运算的指令，如与、或、异或等。在 AVR 微控制器中，目标操作数总是一个寄存器。

**下表显示了逻辑指令:**

<center>

| 指令 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| 和 | d，S | D = D 与 S
对操作数
执行与运算，并将结果存储在左侧操作数中 | 和 D，S |
| ANDI | d，k(常数) | D = D AND k
对操作数
执行 AND 运算，并将结果存储在左手操作数中，右手操作数为常数 | 安迪 D， k |
| 运筹学 | d，S | D = D 或 S
对操作数
执行或运算，并将结果存储在左侧操作数中 | 或 D，S |
| 奥里博卡病毒 | d，k | D = D OR k
对操作数执行 OR 运算
并将结果存储在左手操作数中，右手操作数为常数 | ORI D，k |
| 提高石油采收率 | d，S | D = D 异或 S
对操作数执行异或运算
并将结果存储在左手操作数中 | EOR D，s .公司 |
| 计算机输出缩微胶片 | D. | D = D 的 1 补码
补码动作将“1”变为“0”
，将“0”变为“1” | 通讯设备 | 底片 | D | D = D 的二进制补码
该指令取二进制补码 | 负 D |
| 大脑性麻痹 | d，S | 比较 D 和 S
这个指令真的是一个减法动作。
唯一的区别是寄存器的值不变 | 首席采购官 |
| 消费品价格指数 | d，k | 比较 D 和 k
CP 和 CPI 的唯一区别是
CPI 有一个操作数作为常数 | 页:1 |

</center>

**注:**
D 和 S 分别为目的地和来源。两者都是寄存器。k 是一个常数。