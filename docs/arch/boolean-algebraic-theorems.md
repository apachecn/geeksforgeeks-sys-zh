# 布尔代数定理

> 原文:[https://www.geeksforgeeks.org/boolean-algebraic-theorems/](https://www.geeksforgeeks.org/boolean-algebraic-theorems/)

布尔代数定理是用来改变布尔表达式形式的定理。有时这些定理被用来最小化表达式的项，有时它们只是用来将表达式从一种形式转移到另一种形式。

数字逻辑中有布尔代数定理:

**1。** [**德摩根定理**](https://www.geeksforgeeks.org/properties-of-boolean-algebra/) **:**
德摩根定理代表了布尔代数最重要的两个规则。

```
(i). (A . B)' = A' + B' 
```

因此，变量乘积的补数等于它们各自补数的和。

```
(ii). (A + B)' = A' . B' 
```

因此，变量之和的补数等于它们各自补数的乘积。

上述两个定律可以推广到 n 个变量

```
(A1 . A2 . A3 ... An)' = A1' + A2' + ... + An'

And

(A1 + A2 + ... + An)' = A1' . A2' . A3' ... An' 
```

**2。换位定理:**
它指出:

```
AB + A'C = (A + C) (A' + B)
```

**证明:**

```
RHS 
= (A + C) (A' + B)
= AA' + A'C + AB + CB
= 0 + A'C + AB + BC
= A'C + AB + BC(A + A')
= AB + ABC + A'C + A'BC
= AB + A'C
= LHS 
```

**3。** [**冗余定理**](https://www.geeksforgeeks.org/consensus-theorem-in-digital-logic/) **:**
这个定理是用来剔除冗余项的。一个变量与某个变量相关联，它的补码与另一个变量相关联，下一个项由剩余的变量组成，那么这个项就变得多余了。

**示例:**

```
AB + BC' + AC = AC + BC' 
```

**证明:**

```
LHS 
= AB + BC' + AC
= AB(C + C') + BC'(A + A') + AC(B + B')
= ABC + ABC' + ABC' + A'BC' + ABC + AB'c
= ABC + ABC' + A'BC' + AB'C
= AC(B + B') + BC'(A + A')
= AC + BC'
= RHS 
```

**4。对偶定理:**
对偶表达式相当于写出给定布尔关系的否定逻辑。为此，

1.  将每个“或”符号改为“与”符号，反之亦然。
2.  补充表达式中出现的任何 0 或 1。
3.  保持文字原样。

**示例:**

```
Dual of A(B+C) = A+(B.C) = (A+B)(A+C)
```

**5。互补定理:**
为了获得补码表达式，

1.  将每个“或”符号改为“与”符号，反之亦然。
2.  补充表达式中出现的任何 0 或 1。
3.  补充单个文字。

**示例:**

```
Complement of A(B+C) = A'+(B'.C') = (A'+B')(A'+C')
```