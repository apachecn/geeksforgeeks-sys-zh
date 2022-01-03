# 3NF 和 BCNF 在 DBMS 中的区别

> 原文:[https://www . geeksforgeeks . org/区别-3nf-和-bcnf-in-dbms/](https://www.geeksforgeeks.org/difference-between-3nf-and-bcnf-in-dbms/)

**1。[第三范式(3NF)](https://www.geeksforgeeks.org/third-normal-form-3nf/) :**
如果一个关系处于 [2NF](https://www.geeksforgeeks.org/second-normal-form-2nf/) 中，并且没有非键属性过渡依赖于主键，即没有可传递依赖，则称该关系处于第三范式(3NF)。它还应满足以下给定条件之一。对于函数依赖项 C- > D:

*   c 应该是一把超级钥匙，
*   D 应该是一个主要属性，即 D 应该是候选键的一部分。

3NF 用于减少数据重复并实现数据完整性。

**例:**
对于函数依赖关系为{L- > M，MN- > P，PO- > L}的关系 R(L，M，N，O，P):

```
The candidate keys will be : {LNO, MNO, NOP}
      as the closure of LNO = {L, M, N, O, P} 
             closure of MNO = {L, M, N, O, P}
             closure of NOP = {L, M, N, O, P}
```

这个关系在 3NF 中，因为它已经在 2NF 中，没有传递依赖。也没有非质数属性衍生出非质数属性。

**2。 [Boyce-Codd 范式(BCNF)](https://www.geeksforgeeks.org/boyce-codd-normal-form-bcnf/) :**
BCNF 代表 Boyce-Codd 范式，由 R . F Boyce 和 E . F Codd 于 1974 年提出。如果这些属性成立，则称 BCNF 存在功能依赖关系:

*   应该已经在 3NF 了。
*   对于函数依赖，比如 P->Q，P 应该是一个超级键。

BCNF 是 3NF 的延伸，它比 3NF 有更严格的规则。此外，它被认为比 3NF 更强。

**例:**
对于函数依赖关系为{A- > B，A- > C，C- > D，C- > A}的关系 R(A，B，C，D):

```
The candidate keys will be : {A, C}
      as the closure of A = {A, B, C, D} 
             closure of C = {A, B, C, D} 
```

这种关系是在 BCNF，因为它已经在 3Nf 中(没有主要属性派生没有主要属性)，在函数依赖的左侧有一个候选键。

**3NF 和 BCNF 的区别:**

<center>

| 没有 | 3NF | BCNF(中央银行) |
| --- | --- | --- |
| 1. | 在 3NF 中，不应该有可传递的依赖关系，也就是说，不应该有非质数属性可传递地依赖于候选键。 | 在 BCNF 对于任何关系 A->B，A 都应该是关系的超级键。 |
| 2. | 它没有 BCNF 强大。 | 它比 3NF 相对更强。 |
| 3. | 在 3NF 中，功能依赖已经在 1NF 和 2NF 中。 | 在 BCNF，功能依赖已经存在于 1NF、2NF 和 3NF 中。 |
| 4. | 3NF 中的冗余度很高。 | BCNF 的冗余度相对较低。 |
| 5. | 在 3NF 中，保留了所有的功能依赖。 | 在 BCNF，可能会也可能不会保留所有的功能依赖关系。 |
| 6. | 这相对来说更容易实现。 | 很难实现。 |
| 7. | 3NF 可以实现无损分解。 | 无损分解在 BCNF 很难实现。 |

</center>