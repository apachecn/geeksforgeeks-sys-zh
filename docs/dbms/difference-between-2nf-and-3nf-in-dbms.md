# 数据库管理系统中 2NF 和 3NF 的区别

> 原文:[https://www . geesforgeks . org/difference-2nf-和-3nf-in-dbms/](https://www.geeksforgeeks.org/difference-between-2nf-and-3nf-in-dbms/)

**1。** [**【第二范式(2NF)**](https://www.geeksforgeeks.org/second-normal-form-2nf/) **:**
当一个关系已经处于第一范式，并且不存在部分函数依赖关系，即没有非素属性应该在函数上依赖于素属性时，该关系被称为处于第二范式。它是由 E . F Codd 在 1971 年给出的。如果候选关键字仅包含单个属性，并且关系在 1NF 中，则它已经在 2NF 中。当存在由多个属性组成的复合候选关键字时，2NF 的检查关系的概念适用。

**示例:**
考虑一个具有函数依赖关系的关系 R(A，B，C，D):{ AB–>CD，BC–>D }

```
Closure of (AB)={A, B, C, D} 
```

所以 AB 是候选键。
关系 R 在 1NF，因为关系型 DBMS 不允许多值或复合属性。
在 AB–>CD 中(AB 是候选键，C、D 是非质数)
在 BC–>D 中(BC 是非质数，D 是非质数，这在 2NF 中是允许的)
关系 R 在 2NF 中，因为没有质数属性在导出非质数属性，即不存在[部分函数依赖](https://practice.geeksforgeeks.org/problems/differentiate-between-full-functional-dependency-and-partial-dependency)。
关系 R 不在 3NF 中，因为非素属性正在派生非素属性。

**2。** [**【第三范式(3NF)**](https://www.geeksforgeeks.org/third-normal-form-3nf/) **:**
当一个关系已经处于第一范式和第二范式，并且每个非素属性都非传递依赖于关系的超键，或者简单语言中没有传递函数依赖时，则称该关系处于第三范式。它也是由 E . F Codd 在 1971 年给出的。这种形式减少了数据的重复，保证了引用的完整性。如果下面给出的任一条件为真，则具有函数依赖 A–>B 的关系 R 处于 3NF。

1.  a 是一个超级键。

2.  B 是素属性，即 B 是候选键的一部分。

**示例:-**
考虑一个具有函数依赖关系的关系 R(A，B，C){ AB–>C，C–>A }

```
Closure of (AB)={A, B, C}
Closure of (BC)={A, B, C}
Candidate keys are-{AB, BC} 
```

关系 R 在 1NF 中，因为关系数据库管理系统不允许多值或复合属性。

```
AB-->C(prime deriving prime)
C-->A(prime deriving prime)
```

所以关系 R 在 2NF 和 3NF 中，也是因为不存在素导非素和非素导非素，即不存在部分函数依赖和传递函数依赖。

**2NF 和 3NF 的区别:**

<figure class="table">

| 没有 | 2NF(第二范式) | 3NF(第三范式) |
| --- | --- | --- |
| 1. | 已经在 1NF 了。 | 它已经在 1NF 和 2NF 中了。 |
| 2. | 在 2NF 中，允许非质数属性在功能上依赖于非质数属性。 | 在 3NF 中，非质数属性只允许在功能上依赖于关系的超级键。 |
| 3. | 不允许非质数属性的部分函数依赖于候选关键字的任何适当子集。 | 不允许任何超级键上的非质数属性的可传递函数依赖。。 |
| 4. | 强于 1NF 但小于 3NF 的范式 | 比 1NF 和 2NF 更强的范式。 |
| 5. | 它消除了关系中的重复组。 | 它实际上消除了所有冗余。 |
| 6. | 第二范式的目标是消除冗余数据。 | 第三范式的目标是确保参照完整性。 |

</figure>