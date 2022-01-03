# 计算机组织中的数据操作指令

> 原文:[https://www . geesforgeks . org/data-operation-instructions-in-computer-organization/](https://www.geeksforgeeks.org/data-manipulation-instructions-in-computer-organization/)

**数据操作指令:**
数据操作指令对数据进行操作，为计算机提供计算能力。典型计算机中的数据操作指令通常分为以下三种基本类型。

1.  算术指令
2.  逻辑和位操作指令
3.  换档说明

我们一个一个来讨论。

1.  **Arithmetic instructions :**
    The four basic arithmetic operations are addition, subtraction, multiplication, and division. Most computers provide instructions for all four operations.

    **典型算术指令–**

    <figure class="table">

    | 名字 | 记忆的 | 例子 | 说明 |
    | 增量 | 股份有限公司 | INC B | 它将寄存器 B 增加 1B |
    | 减量 | 数位计算设备公司(Digital Equipment Corporation) | DEC B | 它会将寄存器 B 减 1B |
    | 增加 | 注意缺陷障碍 (Attention Deficit Disorder) | 添加 B | 它会将寄存器 B 的内容添加到累加器的内容中并将结果存储在累加器中交流 |
    | 减去 | 潜水艇 | SUB B | 它将从的内容中减去寄存器 B 的内容

    累加器并将结果存储在累加器中交流 |
    | 乘；成倍增加；（使）繁殖 | MUL | 穆尔 B | 它会将寄存器 B 的内容乘以累加器并将结果存储在累加器中交流 |
    | 划分 | 差异 | DIV B(消歧义) | 它会将寄存器 B 的内容与累加器并将商存储在累加器中交流 |
    | 带进位加法 | add(添加) | addc b(添加 b) | 它会将寄存器 B 的内容和进位标志与累加器的内容并将结果存储在蓄电池交流 |
    | 借减 | SUBB | SUBB 乙 | 它将减去寄存器 B 的内容和进位标志累加器的内容，并将结果存储在蓄电池交流 |
    | 求反(2 的补码) | 底片 | NEG B | 它将通过寻找其单个操作数的 2 的补码来否定一个值。这意味着简单地将操作数乘以-1。B |

    </figure>

2.  **逻辑和位操作指令:**
    逻辑指令对存储在寄存器中的位串执行二进制操作。它们对于操作单个位或一组位很有用。

**典型逻辑和位操作指令–**

<figure class="table">

| 名字 | 记忆的 | 例子 | 说明 |
| 清楚的 | 清除（clear 的缩写） | 清除（clear 的缩写） | 它会将累加器设置为 0AC |
| 补充 | 计算机输出缩微胶片 | COM A | 它将补充累加器上午 |
| 和 | 和 | 和乙 | 它将寄存器 B 的内容与累加器和存储的内容相加它在累加器里交流 |
| 运筹学 | 运筹学 | 或乙 | 它将寄存器 B 的内容与累加器的内容进行 OR 运算并存储在累加器中交流电 |
| 异或 | 异或 | 异或乙 | 它会将寄存器 B 的内容与累加器的内容进行异或运算将其储存在蓄能器中交流 |
| 清除进位 | 贸易委员会 | 贸易委员会 | 它会将进位标志设置为 0进位标志 |
| 设定进位 | set(设置) | set(设置) | 它会将进位标志设置为 1进位标志 |
| 补码进位 | 怎么了 | 怎么了 | 它将补充进位标志进位标志 |
| 启用中断 | 不，不 | 不，不 | 它将启用中断 |
| 禁止中断 | 国防情报部 | 国防情报部 | 它将禁用中断 |

*   **Shift Instructions :**
    Shifts are operations in which the bits of a word are moved to the left or right. Shift instructions may specify either logical shifts, arithmetic shifts, or rotate-type operations.

    **典型换档说明–**

    <figure class="table">

    | 名字 | 记忆的 |
    | 逻辑右移 | share 分享 |
    | 逻辑左移 | 感觉神经性听力丧失 |
    | 算术右移 | SHRA |
    | 算术左移 | 嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘嘘 |
    | 右旋 90 度 | ROR |
    | 左旋 90 度 | 右枕侧位 |
    | 通过进位向右旋转 | 罗里克 |
    | 通过进位向左旋转 | 罗尔克 |

    关于换档指令，请参考本[换档指令参考](https://www.geeksforgeeks.org/shift-micro-operations-in-computer-architecture/)

    </figure>

    </figure>