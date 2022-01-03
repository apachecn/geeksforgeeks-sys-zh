# BCNF 和 4NF 在 DBMS 上的区别

> 原文:[https://www . geesforgeks . org/bcnf-和-4nf-in-dbms 之间的差异/](https://www.geeksforgeeks.org/difference-between-bcnf-and-4nf-in-dbms/)

**1。 [Boyce-Codd 范式(BCNF)](https://www.geeksforgeeks.org/boyce-codd-normal-form-bcnf/) :**
任何关系满足以下条件，则称为在 BCNF:

*   对于每个函数依赖关系 X->Y，X 是给定关系中的[](https://www.geeksforgeeks.org/types-of-keys-in-relational-model-candidate-super-primary-alternate-and-foreign/)。

**2。[第四范式(4NF)](https://www.geeksforgeeks.org/introduction-of-4th-and-5th-normal-form-in-dbms/) :**
任何关系满足以下条件，都称为第四范式:

*   它必须是 Boyce Codd 范式(BCNF)。
*   它应该没有[多值依赖。](https://www.geeksforgeeks.org/multivalued-dependency-mvd-in-dbms/)

当一个表中有两个属性依赖于第三个属性但又相互独立时，称为多值依赖。为了表示多值依赖关系，使用了“->->”这个符号。

**BCNF 和 4NF 的区别:**

<center>

| 没有。 | BCNF(中央银行) | 4NF |
| one | 在 BCNF 的关系也必须在 3NF。 | 4NF 的关系也必须是 Boyce Codd 范式(BCNF)。 |
| Two | BCNF 的关系可能具有多值依赖关系。 | < 4NF 的关系不得有任何多值依赖关系。 |
| three | BCNF 的亲戚可能在 4NF，也可能不在。 | 4NF 的亲戚总是在 BCNF。 |
| four | 与 4NF 相比，BCNF 没有那么强大。 | 与 BCNF 相比，4NF 更强大。 |
| five | 如果一个关系是在 BCNF，那么它将比 4NF 有更多的冗余。 | 如果一个关系是在 4NF，那么与 BCNF 相比，它的冗余会更少。 |
| six | 如果一个关系在 BCNF，那么所有基于功能依赖的冗余都被移除了。 | 如果一个关系在 4NF，那么所有基于函数依赖和多值依赖的冗余都被移除了。 |
| seven | 对于关系，BCNF 的表数小于或等于 4NF 的表数。 | 对于关系，4NF 的表数大于或等于 BCNF 的表数。 |
| eight | 在 BCNF，保持依赖性很难实现。 | 与 BCNF 相比，4NF 更难保持独立。 |
| nine | 在现实世界的数据库设计，一般 3NF 或 BCNF 是首选。 | 在现实世界的数据库设计中，数据库设计者通常不喜欢 4NF。 |
| Ten | BCNF 的关系可能包含多值依赖关系和连接依赖关系。 | 4NF 的关系可能只包含连接依赖关系。 |

</center>