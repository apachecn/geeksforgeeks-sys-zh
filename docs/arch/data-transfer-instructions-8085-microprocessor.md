# 8085 微处理器中的数据传输指令

> 原文:[https://www . geesforgeks . org/data-transfer-instructions-8085-微处理器/](https://www.geeksforgeeks.org/data-transfer-instructions-8085-microprocessor/)

数据传输指令是在微处理器中传输数据的指令。它们也被称为复制指令。

以下是显示逻辑指令列表的表格:

<figure class="table">

| 操作码 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| MOV | Rd，Rs | Rd = Rs | 莫夫 a b |
| MOV | Rd，M | Rd = Mc | MOV A，2050 年 |
| MOV | m，Rs | M = Rs | MOV 2050 年 a |
| MVI | Rd，8 位数据 | Rd = 8 位数据 | MVI A， 50 |
| MVI | m，8 位数据 | M = 8 位数据 | MVI 2050，50 |
| 皱胃向左移 | 16 位地址 | A =地址中的内容 | LDA 2050 |
| 无线电台临时使用许可证 | 16 位地址 | 地址=的内容 | STA 2050 |
| 勒瓦尔德 | 16 位地址 | 直接载入高电平和低电平寄存器 | LHLD 2050 年 |
| 嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘 | 16 位地址 | 直接从高电平寄存器存储 | SHLD 2050 年夏季奥林匹克运动会 |
| LXI | r.p .，16 位数据 | 用数据加载指定的寄存器对 | lxi h 3050 年 |
| LDAX | 公关 | 蓄电池上的间接负载 | LDAX H(消歧义) |
| STAX | 16 位地址 | 从累加器 A 间接存储 | STAX 2050 |
| XCHG 表示 | 没有人 | 用 D 交换 H，用 E 交换 L | XCHG 表示 |
| 推 | 公关 | 将 r.p .推入堆栈 | 推 H |
| 购买凭证（proof of purchase） | 公关 | 将堆栈弹出到 r.p。 | 爸爸 h |
| 在…里 | 8 位端口地址 | 将指定端口的内容输入到 | 15 年 |
| 在外 | 8 位端口地址 | 将的内容输出到指定的端口 | 输出 15 |
|   |   |   |   |

在表中，
R 代表寄存器
M 代表内存
r.p 代表寄存器对

</figure>