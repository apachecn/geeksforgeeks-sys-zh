# AVR 微控制器中的数据传输指令

> 原文:[https://www . geesforgeks . org/data-transfer-instructions-in-AVR-microcontroller/](https://www.geeksforgeeks.org/data-transfer-instructions-in-avr-microcontroller/)

[数据传输指令](https://www.geeksforgeeks.org/data-transfer-instructions-8085-microprocessor/)是将数据传输到[微控制器](https://www.geeksforgeeks.org/introduction-to-8051-microcontroller/)的指令。

**这些指令可用于从:**传输数据

*   **[寄存器到寄存器](https://www.geeksforgeeks.org/register-transfer-language-rtl/):**T5】在寄存器到寄存器的传输中，数据从一个寄存器传输到另一个寄存器。考虑一个必须执行二进制加法的例子。
    **示例–**
    在本例中，第一个数据将传输到 B 寄存器，然后从 B 寄存器传输到累加器寄存器。

    ```
    MVI B, 05
    MOV A, B

    ```

*   **寄存器到内存:**
    在此数据传输中，数据将从寄存器传输到给定的内存位置。考虑一个例子，其中给定的位置是 201k，您必须从累加器中复制数据。
    **示例–**

```
STA 201K

```

*   **内存到寄存器:**
    在本次数据传输中，数据将从内存传输到寄存器。考虑一个例子，其中给定的位置是 201k，您必须将数据从这个内存位置加载到累加器中。
    **示例–**

    ```
    LDA 2020k

    ```

    *   **Constant to Register :**
    In this data transfer, Data will be transferred to the immediate given register. consider an example where given Data is 05 and you have to load data to the accumulator.
    **Example –**

    ```
    MVI A, 05

    ```

    **下表显示了不同的转移指令:**

    <center>

    | 指令 | 操作数 | 说明 | 例子 |
    | --- | --- | --- | --- |
    | MOV | d，S | D = S | 莫夫·d·s·莫夫 |
    | LDS | d，K(内存位置) | D =时的值 | LDS D，K |
    | 致死剂量 | d，S | D =存储在存储单元中的值 | LD D，S |
    | LDI | d，K(常数) | D = K | 迪·d·k |
    | 每分钟列数(ines per minute) | d、Z(闪存) | 将寄存器 Z 中的值从闪存存储到存储在 D 寄存器中的存储位置 | LPM D，z |
    | 在…里 | 丁，甲 | 将值存储在 d 中的寄存器 A 中，其中 A 来自[0，63](64 个输入/输出寄存器) | 在华盛顿特区 |
    | 在外 | 甲、丁 | 将寄存器 D 中的值存储在 A 中
    ，其中 A 来自[0，63](64 个输入/输出寄存器) | 出局 |
    | 成钢 | k，S | 将寄存器 S 中的值存储到存储单元 k 中 | STS K，S |
    | 标准时间（standard time） | d，S | 将寄存器 S 中的值存储到存储在 D 寄存器中的存储位置 | 圣保罗 |
    | 推 | D | 将 D 的内容推到堆栈的顶部 | 推送 |
    | 购买凭证（proof of purchase） | D | 从堆栈中移除最上面的条目
    ，并将该值转移到 D | 爸爸 d |

    </center>

    d 和 S 是寄存器。PUSH 和 POP 指令严格用于维护堆栈。