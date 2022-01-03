# 8086 微处理器中的寻址模式

> 原文:[https://www . geesforgeks . org/addressing-modes-8086-微处理器/](https://www.geeksforgeeks.org/addressing-modes-8086-microprocessor/)

先决条件–[寻址模式](https://www.geeksforgeeks.org/addressing-modes/)、[8085 微处理器中的寻址模式](https://www.geeksforgeeks.org/addressing-modes-8085-microprocessor/)、
通过指令指定要操作的数据的方式称为**寻址模式**。这指定给定的数据是立即数据或地址。它还指定给定的操作数是寄存器还是寄存器对。

寻址模式的类型:

1.  **寄存器模式–**在这种寻址模式下，两个操作数都是寄存器。
    示例:

    ```
    MOV AX, BX
    XOR AX, DX
    ADD AL, BL
    ```

2.  **立即模式–**在这种寻址模式下，源操作数是 8 位或 16 位数据。目标操作数永远不能是立即数据。
    例:

```
MOV AX, 2000
MOV CL, 0A
ADD AL, 45
AND AX, 0000
```

注意，要初始化段寄存器的值，需要一个寄存器。

```
MOV AX, 2000
MOV CS, AX 
```

*   **位移或直接模式–**在这种寻址模式下，有效地址直接在指令中作为位移给出。
    示例:

    ```
    MOV AX, [DISP]
    MOV AX, [0500]
    ```

    *   **注册间接模式–**在这种寻址模式下，有效地址为国际单位制、国际单位制或 BX。
    示例:

    ```
    MOV AX, [DI]
    ADD AL, [BX]
    MOV AX, [SI] 
    ```

    *   **Based indexed mode –** In this the effective address is sum of base register and index register.

    ```
    Base register: BX, BP
    Index register: SI, DI 
    ```

    物理内存地址是根据基址寄存器计算的。
    例:

    ```
    MOV AL, [BP+SI]
    MOV AX, [BX+DI]
    ```

    *   **索引模式–**在这种寻址模式下，有效地址是索引寄存器和位移的总和。
    示例:

    ```
    MOV AX, [SI+2000]
    MOV AL, [DI+3000]
    ```

    *   **基模式–**在这种情况下，有效地址是基寄存器和位移的总和。
    示例:

    ```
    MOV AL, [BP+ 0100]
    ```

    *   **基于索引的移位模式–**在这种寻址模式中，有效地址是索引寄存器、基址寄存器和移位的总和。
    示例:

    ```
    MOV AL, [SI+BP+2000] 
    ```

    *   **字符串模式–**该寻址模式与字符串指令相关。在这种情况下，SI 和 DI 的值根据方向标志的值自动递增和递减。
    示例:

    ```
    MOVS B
    MOVS W 
    ```

    *   **输入/输出模式–**该寻址模式与输入输出操作相关。
    示例:

    ```
    IN A, 45
    OUT A, 50 
    ```

    *   **相对模式–**
    在这种模式下，有效地址是参照指令指针计算的。
    例:

    ```
    JNZ 8 bit address
    IP=IP+8 bit address 
    ```