# 8085 微处理器中的逻辑指令

> 原文:[https://www . geesforgeks . org/logic-instructions-8085-微处理器/](https://www.geeksforgeeks.org/logical-instructions-8085-microprocessor/)

逻辑指令是执行诸如“与”、“或”等基本逻辑操作的指令。在 8085 微处理器中，目标操作数总是累加器。这里，逻辑运算在逐位级别上工作。

下表显示了逻辑指令列表:

| 操作码 | 操作数 | 目的地 | 例子 |
| --- | --- | --- | --- |
| 语录 | 稀有 | A = A 和 R | 安娜 b |
| 语录 | M | A = A 和 Mc | 全日空 2050 |
| 犀鹃 | 8 位数据 | 8 位数据 | ANI 50 |
| 奥拉 | 稀有 | A = A 或 R | 现在 b |
| 奥拉 | M | A = A 或 Mc | ORA 2050 |
| 奥里博卡病毒 | 8 位数据 | 8 位数据 | ORI 50 |
| XRA | 稀有 | 一个异或 | XRA B |
| XRA | M | 异或 Mc | XRA 2050 |
| XRI | 8 位数据 | 异或 8 位数据 | XRI 50 |
| 军事委员会(Committee of Military Affairs) | 没有人 | A = 1 对 A 的称赞 | 军事委员会(Committee of Military Affairs) |
| 金属波纹管(Corrugated Metal Pipe) | 稀有 | 将 R 与 A 进行比较，并触发标志寄存器 | 《议定书》/《公约》缔约方会议 |
| 金属波纹管(Corrugated Metal Pipe) | M | 将 Mc 与 A 进行比较，并触发标志寄存器 | 《议定书》/《公约》缔约方会议 2050 年 |
| 消费品价格指数 | 8 位数据 | 将 8 位数据与 A 进行比较，并触发标志寄存器 | 消费物价指数 50 |
| （Ladyofthe）RoyalRedCross（英国）皇家护士红十字勋章（获得者） | 没有人 | 不带进位向右旋转累加器 | （Ladyofthe）RoyalRedCross（英国）皇家护士红十字勋章（获得者） |
| RLC | 没有人 | 不带进位向左旋转累加器 | RLC |
| RAR | 没有人 | 带进位向右旋转累加器 | RAR |
| RAL | 没有人 | 带进位向左旋转累加器 | RAR |
| 计算机媒介交流 | 没有人 | 向国旗致敬 | 计算机媒介交流 |
| 卫星追踪委员会(Satellite Tracking Committee) | 没有人 | 设置进位标志 | 卫星追踪委员会(Satellite Tracking Committee) |

在表中，
R 代表寄存器
M 代表内存
Mc 代表内存内容

阅读相关帖子:[8085 微处理器](https://www.geeksforgeeks.org/arithmetic-instructions-8085-microprocessor/)中的算术指令