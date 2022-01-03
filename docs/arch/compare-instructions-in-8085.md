# 比较 8085

中的说明

> 原文:[https://www.geeksforgeeks.org/compare-instructions-in-8085/](https://www.geeksforgeeks.org/compare-instructions-in-8085/)

**COMPARE** 是 8085 微处理器中广泛使用的重要指令。8085 指令集有两种比较操作:与累加器比较和立即与累加器比较。

微处理器通过从(A)中减去数据字节来比较数据字节(或寄存器/存储器内容)和累加器的内容，并通过修改标志来指示数据字节是否小于、大于或等于累加器的内容。但是，内容不会被修改。下一节将简要说明两种类型的比较指令:

1.  **Compare (register or memory) with accumulator (CMP R/M) –**
    This is a 1-byte instruction. It compares the data byte in the register or memory with the contents of accumulator.
    1.  如果 A 小于(R/M)，则设置 CY 标志并重置零标志。
    2.  如果 A 等于(R/M)，则置零标志并复位 CY 标志。
    3.  如果大于，则重置 CY 和 Zero 标志。

    当内存是操作数时，其地址由 HL 对指定。没有修改任何内容；然而，根据减法的结果，所有剩余的标志(S、P、AC)都会受到影响。

    **示例:**
    让寄存器 B 包含数据字节 62H，累加器 A 包含 57H。然后，

    ```
    Instruction- CMP B
    Before execution: A = 57, B = 62
    After execution: A = 57, B = 62   
    ```

    标志:由于 A 小于 B，因此设置 CY，重置 Z 标志。

    ```
    CY=1, Z=0 
    ```

2.  **Compare immediate with accumulator (CPI 8-bit) –**
    This is a 2-byte instruction, the second byte being 8-bit data. It compares the second byte with the contents of accumulator.
    1.  如果 A 小于 8 位数据，则设置 CY 标志，重置 Zero 标志。
    2.  如果 A 等于 8 位数据，则置零标志并复位 CY 标志。
    3.  如果 A 大于 8 位数据，则 CY 和 Zero 标志复位。

    没有修改任何内容；然而，根据减法的结果，所有剩余的标志(S、P、AC)都会受到影响。

    **例:**
    让累加器 A 包含 C2H。然后，

    ```
    Instruction- CPI C2H
    Before execution: A = C2, B = C2
    After execution: A = C2, B = C2  
    ```

    标志:由于 A 等于数据字节，因此 Z 被置位，CY 标志被复位。

    ```
    CY=0, Z=1 
    ```