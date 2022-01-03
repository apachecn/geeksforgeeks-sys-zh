# 8086 微处理器的标志寄存器

> 原文:[https://www . geesforgeks . org/flag-register-8086-微处理器/](https://www.geeksforgeeks.org/flag-register-8086-microprocessor/)

先决条件–[8085 微处理器中的标志寄存器](https://www.geeksforgeeks.org/flag-register-8085-microprocessor/)
标志寄存器是一个专用寄存器。根据任何算术和逻辑运算后的结果值，标志位变为置位(1)或复位(0)。

![](img/982524958f163517acc1619825e8c0c9.png)
**图–**标志寄存器格式
8086 共有 9 个标志，标志寄存器分为两种类型:

**(a)状态标志–**8086 微处理器中有 6 个标志寄存器，根据 8 位或 16 位操作后的情况，这些寄存器变为置位(1)或复位(0)。这些标志是条件/状态标志。其中 5 个标志与 8085 微处理器的情况相同，它们的工作也与 8085 微处理器相同。第六个是溢出标志。

6 个状态标志是:

1.  **标志标志**
2.  **零标志(Z)**
3.  **辅助卡里旗(AC)**
4.  **奇偶校验标志(P)**
5.  **扛旗(CY)**
    这前[五旗在这里定义](https://www.geeksforgeeks.org/flag-register-8085-microprocessor/)
6.  **Overflow Flag (O) –** This flag will be set (1) if the result of a signed operation is too large to fit in the number of bits available to represent it, otherwise reset (0). After any operation, if D[6] generates any carry and passes to D[7] OR if D[6] does not generates carry but D[7] generates, overflow flag becomes set, i.e., 1\. If D[6] and D[7] both generate carry or both do not generate any carry, then overflow flag becomes reset, i.e., 0.

    **示例:**添加字节 100 + 50 时(结果不在-128…127 范围内)，将设置溢出标志。

    ```
    MOV AL, 50 (50 is 01010000 which is positive)
    MOV BL, 32 (32 is 00110010 which is positive)
    ADD AL, BL (82 is 10000010 which is negative)

    ```

    当我们添加 2 +ve 个数字时，溢出标志被设置，我们得到一个-ve 个数字。

**(b)控制标志–**控制标志启用或禁用微处理器的某些操作。8086 微处理器中有 3 个控制标志，它们是:

1.  **方向标志(D)–**该标志专门用于字符串指令。
    如果方向标志设置为(1)，则从较高的存储位置向较低的存储位置访问字符串数据。
    如果方向标志复位(0)，则从较低的存储位置向较高的存储位置访问字符串数据。
2.  **中断标志(I)–**该标志用于中断。
    如果中断标志被设置(1)，微处理器将识别来自外围设备的中断请求。
    如果中断标志复位(0)，微处理器将不识别任何中断请求，并将忽略它们。
3.  **陷阱标志(T)–**该标志用于片内调试。设置陷阱标志使微处理器进入单步调试模式。单步执行时，微处理器执行一条指令并进入单步中断服务。
    如果陷阱标志设置为(1)，则中央处理器在每条指令后自动生成一个内部中断，允许程序在逐个指令执行时被检查。
    如果陷阱标志复位(0)，则不执行任何功能。