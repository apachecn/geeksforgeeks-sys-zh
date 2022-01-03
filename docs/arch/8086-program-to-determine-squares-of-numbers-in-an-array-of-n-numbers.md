# 8086 确定 n 个数字数组中数字平方的程序

> 原文:[https://www . geeksforgeeks . org/8086-程序确定数字数组中的数字平方/](https://www.geeksforgeeks.org/8086-program-to-determine-squares-of-numbers-in-an-array-of-n-numbers/)

**问题–**在 8086 微处理器中编写一个程序，找出 8 位 n 个数的平方，其中大小“n”存储在偏移量 500 处，个数从偏移量 501 开始存储，并将结果数存储到偏移量 501 中。(假设正方形的长度只有 8 位)。

**示例–**

![](img/ce5267e9f11762c3f6c6beb97d33aa19.png)

**算法–**

1.  将 500 存储到 SI，并将偏移量 500 的数据加载到寄存器 CL，并将寄存器 CH 设置为 00(用于计数)。
2.  将 SI 值增加 1。
3.  从下一个偏移量(即 501)加载第一个数字(值)到寄存器 a1。
4.  将寄存器 A1 中的值乘以自身。
5.  将结果(寄存器 A1 的值)存储到存储器偏移 SI。
6.  将 SI 值增加 1。
7.  循环 2 以上，直到 CX 寄存器得到 0。

**程序–**

<center>

| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| four hundred | MOV 是，500 | 国际标准 |
| Four hundred and three | mov cl 是] | cl |
| Four hundred and five | 莫夫·契尔 | CH |
| Four hundred and seven | 国际公司 | SI |
| Four hundred and eight | MOV AL，[是] | al |
| 40A | 穆尔阿尔 | ax=al * |
| 40C | mov[是]，AL | al >[是] |
| 40E | 国际公司 | SI |
| 40F | 回路 408 | 跳到 408 IF CX！=0，CX=CX-1 |
| Four hundred and eleven | HLT | 结束 |

</center>

**解释–**

1.  **MOV SI，500:** 将 SI 的值设置为 500
2.  **MOV CL、【SI】:**从偏移 SI 向寄存器 CL 加载数据
3.  **MOV 通道，00:** 将寄存器通道的值设置为 00
4.  **INC SI:**SI 值增加 1。
5.  **MOV a1、【SI】:**从偏移 SI 到寄存器 a1 的加载值
6.  **MUL a1:**寄存器 a1 的值乘以 a1。
7.  **MOV[S1]，A1:**存储偏移量 S1 处寄存器 A1 的值。
8.  **INC SI:**SI 值增加 1。
9.  **循环 408:** 如果 CX 不是 0，CX=CX-1，跳转到地址 408。
10.  **HLT:** 停止