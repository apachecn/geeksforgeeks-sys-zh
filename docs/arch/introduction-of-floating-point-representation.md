# 浮点表示法介绍

> 原文:[https://www . geesforgeks . org/浮点表示法简介/](https://www.geeksforgeeks.org/introduction-of-floating-point-representation/)

**1。为了将浮点转换为十进制，我们在 32 位浮点表示中有 3 个元素:**
i)符号
ii)指数
iii)尾数

*   **符号**位是二进制表示的第一位。“1”表示负数，“0”表示正数。
    **例:**1100000111010000000000000000000000000000000000000000000000000000000000000000000000000000
*   **Exponent** is decided by the next 8 bits of binary representation. 127 is the unique number for 32 bit floating point representation. It is known as bias. It is determined by 2<sup>k-1</sup> -1 where ‘k’ is the number of bits in exponent field. 

    8 位表示中有 3 个指数位，32 位表示中有 8 个指数位。

    因此

    8 位转换偏置= 3(2<sup>3-1</sup>-1 = 4-1 = 3)
    32 位转换偏置= 127。(2 <sup>8-1</sup> -1 = 128-1 = 127)

    **例:**0100000111010000000000000000000
    100000011 =(131)<sub>10</sub>T5】131-127 = 4

    因此 2 的指数将是 4，即 2 <sup>4</sup> = 16。

*   **Mantissa** is calculated from the remaining 23 bits of the binary representation. It consists of ‘1’ and a fractional part which is determined by: 

    **示例:**

    01000001110100000000000000000000 

    尾数的小数部分由下式给出:

    1*(1/2) + 0*(1/4) + 1*(1/8) + 0*(1/16) +……… = 0.625 

    因此尾数将是 1 + 0.625 = 1.625

    因此给出的十进制数为:符号*指数*尾数= (-1) <sup>0</sup> *(16)*(1.625) = 26

**2。为了将十进制转换为浮点，我们在 32 位浮点表示中有 3 个元素:**
i)符号(MSB)
ii)指数(MSB 后 8 位)
iii)尾数(剩余 23 位)

*   **符号位**是二进制表示的第一位。“1”表示负数，“0”表示正数。
    示例:将-17 转换为 32 位浮点表示符号位= 1
*   **Exponent** is decided by the nearest smaller or equal to 2<sup>n</sup> number. For 17, 16 is the nearest 2<sup>n</sup>. Hence the exponent of 2 will be 4 since 2<sup>4</sup> = 16\. 127 is the unique number for 32 bit floating point representation. It is known as bias. It is determined by 2<sup>k-1</sup> -1 where ‘k’ is the number of bits in exponent field. 

    因此，32 位偏置= 127。(2 <sup>8-1</sup> -1 = 128-1 = 127)

    现在，127 + 4 = 131，即二进制表示中的 10000011。

*   **Mantissa:** 17 in binary = 10001.

    移动二进制点，使其只剩下一位。调整 2 的指数，使数值不变。这是标准化的数字。1.0001×2<sup>4</sup>。现在，考虑小数部分，通过添加零表示为 23 位。

    00010000000000000000000

相关链接:
[https://www.youtube.com/watch?v=03fhijH6e2w](https://www.youtube.com/watch?v=03fhijH6e2w)

更多关于数字表示的问题:
[https://www.geeksforgeeks.org/number-representation-gq/](https://www.geeksforgeeks.org/number-representation-gq/)

本文由**克里提·库什瓦哈**供稿

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。