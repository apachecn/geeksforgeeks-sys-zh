# 微处理器中的指令字大小

> 原文:[https://www . geesforgeks . org/指令字大小的微处理器/](https://www.geeksforgeeks.org/instruction-word-size-in-microprocessor/)

8085 指令集根据指令的长度分为 3 类。在 8085 中，长度是用“字节”而不是“字”来衡量的，因为 8085 微处理器有 8 位数据总线。三种类型的指令是:1 字节指令、2 字节指令和 3 字节指令。

**1。一字节指令–**
在一字节指令中，指令的操作码和操作数用一个字节表示。

*   **示例-1:**
    任务-复制寄存器 b 中累加器的内容

    ```
    Mnemonic- MOV B, A
    Opcode- MOV
    Operand- B, A
    Hex Code- 47H
    Binary code- 0100 0111 
    ```

*   **示例-2:**
    任务-将累加器的内容添加到寄存器 b 的内容中

```
 Mnemonic- ADD B
Opcode- ADD
Operand- B
Hex Code- 80H
Binary code- 1000 0000 
```

*   **Example-3:**
    Task- Invert (complement) each bit in the accumulator.

    ```
    Mnemonic- CMA
    Opcode- CMA
    Operand-  NA
    Hex Code- 2FH
    Binary code- 0010 1111 
    ```

    **注意–**这些指令的长度为 8 位；每个都需要一个存储位置。助记符后面总是有一个字母(或两个字母)代表寄存器(如 A、B、C、D、E、H、L 和 SP)。

    **2。双字节指令–**
    双字节指令是一种指令类型，其中前 8 位表示操作码，后 8 位表示操作数。

    *   **示例-1:**
        任务-在累加器中加载十六进制数据 32H。

        ```
        Mnemonic- MVI A, 32H
        Opcode- MVI
        Operand- A, 32H
        Hex Code- 3E
        32
        Binary code- 0011 1110
        0011 0010 
        ```

    *   **示例-2:**
        任务-加载寄存器 b 中的十六进制数据 F2H。

        ```
        Mnemonic- MVI B, F2H
        Opcode- MVI
        Operand- B, F2H
        Hex Code- 06
        F2
        Binary code- 0000 0110
        1111 0010 
        ```

    **注意–**这种类型的指令需要两个字节来存储二进制代码。助记符后面总是跟着 8 位(字节)数据。

    **3。三字节指令–**
    三字节指令是一种指令类型，其中前 8 位表示操作码，后两个字节指定 16 位地址。低位地址用第二个字节表示，高位地址用第三个字节表示。

    *   **示例-1:**
        任务-将内存 2050H 的内容加载到累加器中。

        ```
        Mnemonic- LDA 2050H
        Opcode- LDA
        Operand- 2050H
        Hex Code- 3A
        50
        20
        Binary code- 0011 1010
        0101 0000
        0010 0000 
        ```

    *   **示例-2:**
        任务-将程序序列转移到内存位置 2050H。

        ```
        Mnemonic- JMP 2085H
        Opcode- JMP
        Operand- 2085H
        Hex Code- C3
        85
        20
        Binary code- 1100 0011
        1000 0101
        0010 0000 
        ```

    **注意–**这些指令需要三个存储位置来存储二进制代码。助记符后面总是跟着 16 位(或 adr)。