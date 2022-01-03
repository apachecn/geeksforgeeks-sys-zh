# 8085

中的旋转指令

> 原文:[https://www.geeksforgeeks.org/rotate-instructions-in-8085/](https://www.geeksforgeeks.org/rotate-instructions-in-8085/)

**ROTATE** 是 8085 微处理器的逻辑运算。这是一个 1 字节的指令。该指令在操作码后不需要任何操作数。它操作累加器的内容，结果也存储在累加器中。旋转指令用于旋转累加器的位。

**ROTATE 指令的类型:**
ROTATE 指令有 4 类:向左旋转累加器(RLC)，向左旋转累加器通过进位(RAL)，向右旋转累加器(RRC)，向右旋转累加器通过进位(RAR)。这四个指令中；两个用于向左旋转，两个用于向右旋转。所有这些都将在以下章节中简要说明:

1.  **向左旋转累加器(RLC)–**
    在此指令中，每一位都移动到相邻的左侧位置。位 D7 变为 D0。进位标志 CY 根据位 D7 进行修改。例如:-

    ```
    A = D7 D6 D5 D4 D3 D2 D2 D0

    //before the instruction
    A = 10101010; CY=0  

    //after 1st RLC           
    A = 01010101; CY=1      

    //after 2nd RLC 
    A = 10101010; CY=0 
    ```

2.  **通过进位(RAL)–**
    向左旋转累加器在此指令中，每个位被移到相邻的左边位置。位 D7 成为进位位，进位位被移入 D0。进位标志 CY 根据位 D7 进行修改。例如:

```
A = D7 D6 D5 D4 D3 D2 D2 D0

//before the instruction
A = 10101010; CY=0 

//after 1st RAL
A = 01010100; CY=1

//after 2nd RAL
A = 10101001; CY=0 
```

*   **向右旋转累加器(RRC)–**
    在此指令中，每个位都被移到相邻的右位置。位 D7 变为 D0。进位标志 CY 根据位 D0 进行修改。例如:

    ```
    A = D7 D6 D5 D4 D3 D2 D2 D0

    //before the instruction
    A = 10000001; CY=0     

    //after 1st RRC        
    A = 11000000; CY=1    

    //after 2nd RRC         
    A = 01100000; CY=0 
    ```

    *   **Rotate accumulator right through carry (RAR) –**
    In this instruction, each bit is shifted to the adjacent right position. Bit D0 becomes the carry bit and the carry bit is shifted into D7\. Carry flag CY is modified according to the bit D0\. For example:

    ```
    A = D7 D6 D5 D4 D3 D2 D2 D0

    //before the instruction
    A = 10000001; CY=0  

    //after 1st RAR           
    A = 01000000; CY=1   

    //after 2nd RAR          
    A = 10100000; CY=0 
    ```

    **旋转指令的应用:**
    旋转指令主要用于算术乘法和除法运算以及串行数据传输。例如:

    ```
    If A is 0000 1000 = 08H 

    1\. By rotating 08H right : A = 0000 0100 = 04H
        This is equivalent to *dividing by 2*.

    2\. By rotating 08H left : A = 0001 0000 = 10H
        This is equivalent to *multiplying by 2*. 
    ```

    但是，当逻辑 1 从 D7 向左旋转到 D0 时，这些过程无效，反之亦然。例如，如果向左旋转 80H，它将变成 01H。