# 8086 微处理器中的通用寄存器

> 原文:[https://www . geeksforgeeks . org/通用寄存器-8086-微处理器/](https://www.geeksforgeeks.org/general-purpose-registers-8086-microprocessor/)

通用寄存器用于在微处理器中存储临时数据。8086 微处理器中有 8 个通用寄存器。

![](img/ffff213b961c7f8600d2edbb6a19a1fb.png)

<center>**Figure** – General purpose registers</center>

1.  **AX –** This is the accumulator. It is of 16 bits and is divided into two 8-bit registers AH and AL to also perform 8-bit instructions.
    It is generally used for arithmetical and logical instructions but in 8086 microprocessor it is not mandatory to have accumulator as the destination operand.

    示例:

    ```
    ADD AX, AX (AX = AX + AX)
    ```

2.  **BX –** This is the base register. It is of 16 bits and is divided into two 8-bit registers BH and BL to also perform 8-bit instructions.
    It is used to store the value of the offset.

    示例:

    ```
    MOV BL, [500] (BL = 500H)
    ```

3.  **CX –** This is the counter register. It is of 16 bits and is divided into two 8-bit registers CH and CL to also perform 8-bit instructions.
    It is used in looping and rotation.

    示例:

    ```
    MOV CX, 0005
    LOOP

    ```

4.  **DX –** This is the data register. It is of 16 bits and is divided into two 8-bit registers DH and DL to also perform 8-bit instructions.
    It is used in multiplication an input/output port addressing.

    示例:

    ```
    MUL BX (DX, AX = AX * BX)

    ```

5.  **SP–**这是堆栈指针。它是 16 位的。
    它指向堆栈的最顶层。如果堆栈是空的，堆栈指针将是(FFFE)H。它是相对于堆栈段的偏移地址。
6.  **BP–**这是基础指针。它是 16 位的。
    主要用于访问堆栈传递的参数。它是相对于堆栈段的偏移地址。
7.  **SI–**这是源索引寄存器。它是 16 位的。
    用于数据的指针寻址和一些字符串相关操作的源。它的偏移量是相对于数据段的。
8.  **DI–**这是目标索引寄存器。它是 16 位的。
    用于数据的指针寻址和一些字符串相关操作的目的地。它的偏移量是相对于额外的段。