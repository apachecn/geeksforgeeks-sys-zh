# 8085 微处理器中的寻址模式

> 原文:[https://www . geesforgeks . org/addressing-modes-8085-微处理器/](https://www.geeksforgeeks.org/addressing-modes-8085-microprocessor/)

先决条件–[寻址模式](https://www.geeksforgeeks.org/addressing-modes/)
指定指令要操作的数据的方式称为寻址模式。

**寻址模式类型–**
在 8085 微处理器中，有 5 种寻址模式:

1.  **Immediate Addressing Mode –** 
    In immediate addressing mode the source operand is always data. If the data is 8-bit, then the instruction will be of 2 bytes, if the data is of 16-bit then the instruction will be of 3 bytes. 

    **示例:**
    MVI B 45(立即将数据 45H 移动到寄存器 B)
    LXI H 3050(立即用操作数 3050H 加载 H-L 对)
    JMP 地址(立即跳转到操作数地址)

2.  **Register Addressing Mode –** 
    In register addressing mode, the data to be operated is available inside the register(s) and register(s) is(are) operands. Therefore the operation is performed within various registers of the microprocessor. 

    **示例:**
    MOV A、B(将寄存器 B 的内容移到寄存器 A)
    ADD B(将寄存器 A 和 B 的内容相加并将结果存储在寄存器 A 中)
    INR A(将寄存器 A 的内容递增 1)

3.  **Direct Addressing Mode –** 
    In direct addressing mode, the data to be operated is available inside a memory location and that memory location is directly specified as an operand. The operand is directly available in the instruction itself. 

    **示例:**
    LDA 2050(将存储单元的内容加载到累加器 A 中)
    LHLD 地址(将 16 位存储单元的内容加载到 H-L 寄存器对中)
    IN 35(从地址为 35 的端口读取数据)

4.  **Register Indirect Addressing Mode –** 
    In register indirect addressing mode, the data to be operated is available inside a memory location and that memory location is indirectly specified by a register pair. 

    **示例:**
    MOV A，M(将 H-L 对指向的内存位置的内容移动到累加器)
    LDAX B(将 B-C 寄存器的内容移动到累加器)
    LXIH 9570(立即加载带有位置 9570 地址的 H-L 对)

5.  **Implied/Implicit Addressing Mode –** 
    In implied/implicit addressing mode the operand is hidden and the data to be operated is available in the instruction itself. 

    **示例:**
    CMA(查找并存储 A 中累加器 A 内容的 1 的补码)
    RRC(向右旋转累加器 A 一位)
    RLC(向左旋转累加器 A 一位)