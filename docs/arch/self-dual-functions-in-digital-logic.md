# 数字逻辑中的自身双重功能

> 原文:[https://www . geesforgeks . org/self-双功能数字逻辑/](https://www.geeksforgeeks.org/self-dual-functions-in-digital-logic/)

一个函数被称为**自对偶**当且仅当它的对偶等价于给定的函数，即如果给定的函数是 **f(X，Y，Z) = (XY + YZ + ZX)** ，那么它的对偶就是， **fd(X，Y，Z) = (X + Y)。(Y + Z)。(Z + X)** (fd =给定函数的对偶)= **(XY + YZ + ZX)** ，相当于给定函数。所以功能是自我双重的。

在双重功能中:

1.  给定函数的“与”运算符变为“或”运算符，反之亦然。
2.  给定函数的常数 1(或真)变为常数 0(或假)，反之亦然。

在下列情况下，开关函数或布尔函数称为自对偶函数:

1.  给定的函数是中性的，即(最小项数等于最大项数)。有关最小项和最大项的更多信息(参见[规范和标准形式](https://www.geeksforgeeks.org/digital-logic-canonical-standard-form/))。
2.  该函数不包含两个互斥的术语。

**注:**XYZ 互斥术语为(X'Y'Z ')，即 XYZ 的补语。所以，两个互相排斥的术语是相辅相成的。

**例:**

<figure class="table">

| SL 号 | X | Y | Z |
| --- | --- | --- | --- |
| Zero | Zero | Zero | Zero |
| one | Zero | Zero | one |
| Two | Zero | one | Zero |
| three | Zero | one | one |
| four | one | Zero | Zero |
| five | one | Zero | one |
| six | one | one | Zero |
| seven | one | one | one |

在上表中，互斥术语是:

```
(0,7), (1,6), (2,5), (3,4) 
```

**说明:**

*   (000)的补码，即 0 是(111)，即 7，所以，(0，7 互相排斥。)
*   (001)的补码，即 1 是(110)即 6 所以，(1，6)是互相排斥的。)
*   (010)的补码，即 2 是(101)，即 5 所以，(2，5 是互相排斥的。)
*   (011)的补码，即 3 是(100)，即 4 所以，(3，4 是互相排斥的。)

现在，让我们检查给定函数可能的自对偶函数的数量。
假设，一个函数有 **n 个**变量，

```
 Number of pairs possible = 2n/2 = 2(n-1)
```

因此，自对偶函数的数量可以用 **n** 个变量来表示

```
= 22(n-1) 
```

每对有 2 种可能。

**例:**有 3 个变量 X，Y，Z 的函数的自对偶总数是多少？

```
= 22(3-1) 
= 222
= 24
= 16 
```

**注:**

1.  每个自对偶函数都是中性的，但每个中性函数都不是自对偶的。
2.  自对偶在补集下是封闭的，即自对偶函数的补集也是自对偶的。

</figure>