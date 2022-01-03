# 负二进制数的表示

> 原文:[https://www . geeksforgeeks . org/负数的表示/](https://www.geeksforgeeks.org/representation-of-negative-binary-numbers/)

由于[二进制数](https://www.geeksforgeeks.org/binary-representation-of-a-given-number/)每个位置或位只能有两个符号 0 或 1，因此不可能在二进制数前面加上减号或加号。

我们用一个减号代表负二进制数。在计算机数字表示法中，这些数字可以借助于一个额外的位或标志来区分，这个位或标志在有符号数字的二进制数字表示系统中称为符号位或符号标志。这个额外的位称为符号位或符号标志，对于正数，符号位的值为 0，对于负二进制数，符号位的值为 1。

正数大小的表示很容易，不需要任何改变。

负数的大小的表示相应地改变以表示它。

**表示量值的方法:**
这些是:符号-量值法、1 的补码法、2 的补码法。这些用例子解释如下。

1.  **Signed Magnitude Method :**
    We only add an extra sign bit to recognize negative and positive numbers. Sign bit has 1 for negative number and 0 for positive number.

    ![](img/92bbd69d1fc774790863abe8c1176d6a.png)

    **数字范围:**
    对于 n 位寄存器，MSB 为符号位，而(n-1)位为幅度位。那么，
    可以存储的负最低数为-(2 <sup>(k-1)</sup> -1)，可以存储的正最大数为(2 <sup>(k-1)</sup> -1)。

    但是，这个(符号)表示有一个不明确的数字 0 表示。这意味着 0 有两种不同的表示，一种是-0(例如，六位寄存器中的 1 00000)，第二种是+0(例如，六位寄存器中的 00000)。

    ![](img/5b486645dfeb97454ab7efb1e1ff79ba.png)

2.  **[1’s Complement](https://www.geeksforgeeks.org/find-ones-complement-integer/) Method :**
    Please note that MSB is always Sign bit, if it 0, then there are no changes. MSB is always 1 in case of negative numbers. We only take 1’s complement of negative numbers to represent in the computer.

    ![](img/9f994e6bd9c43f8a84076eddf24b4b40.png)

    **数字范围:**
    对于 n 位寄存器，可以存储的最低负数为-(2 <sup>(n-1)</sup> -1)，可以存储的最大正数为(2 <sup>(n-1)</sup> -1)。

    但是，这个(符号)表示有一个不明确的数字 0 表示。这意味着 0 有两种不同的表示，一种是-0(例如，五位寄存器中的 1 1111)，第二种是+0(例如，五位寄存器中的 0 0000)。

    ![](img/d18960306b9e322f4017092c1e1dc500.png)

3.  **[2’s Complement](https://www.geeksforgeeks.org/efficient-method-2s-complement-binary-string/) Method :**
    Please note that MSB is always Sign bit, if it 0, then there are no changes. MSB is always 1 in case of negative numbers. We only take 2’s complement of negative numbers to represent in the computer.

    ![](img/8e0d5db77722792f43e686678bc1c161.png)

    因为+0 和-0 只有一种表示，所以这个 2 的补码表示比符号表示和 1 的补码表示好。

    ![](img/b0d4e56b49e72a7a8f47f7a5950a9bd7.png)

    **数字范围:**
    对于 n 位寄存器，可以存储的最低负数为-(2 <sup>(n-1)</sup> )，可以存储的最大正数为(2 <sup>(n-1)</sup> -1)。