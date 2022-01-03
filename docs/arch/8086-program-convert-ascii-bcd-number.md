# 8086 程序将 8 位 ASCII 码转换为 BCD 号

> 原文:[https://www . geesforgeks . org/8086-program-convert-ascii-BCD-number/](https://www.geeksforgeeks.org/8086-program-convert-ascii-bcd-number/)

**问题–**编写程序将 ASCII 转换为 BCD 8 位数字，起始地址为 **2000** ，数字存储在 **2050** 内存地址，并将结果存储到 **3050** 内存地址。

```
Example-
Input  : location: 2050
         Data   : 37
Output : location: 3050    
         Data   : 07        
```

**算法–**

1.  Move the value of [2050] into AL
2.  Use 0F
3.  The AND operation on AL shifts the contents of accumulator AL into 3050.
4.  stop

**程序–**

| 记忆 | 记忆术 | 操作数 |  |
| --- | --- | --- | --- |
| 【2000】 | 【mov】 | 【al】【2050】 | 【al】【2050】 |
|  |

**解释–**寄存器 a1 用于通用

1.  **MOV** is used to transmit data.
2.  **Used for multiplication (logically)**
***   **HLT** is used to pause the program.**