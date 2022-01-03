# 关系代数和关系微积分的区别

> 原文:[https://www . geeksforgeeks . org/关系代数与关系演算之间的区别/](https://www.geeksforgeeks.org/difference-between-relational-algebra-and-relational-calculus/)

**关系代数**和**关系演算**都是形式查询语言。

**[关系代数](https://www.geeksforgeeks.org/database-management-system-relational-algebra/) :**
关系代数是一种程序语言。在关系代数中，指定了操作必须执行的顺序。在关系代数中，框架被创建来实现查询。关系代数中包含基本操作有:

```
1. Select (σ)
2. Project (Π)
3. Union (U)
4. Set Difference (-)
5. Cartesian product (X)
6. Rename (ρ) 
```

**关系演算:**
关系演算是正式的查询语言。它也被称为**陈述性语言**。在关系演算中，没有指定操作必须执行的顺序。关系演算意味着我们必须获得什么结果。
关系演算有两种变体:

1.  [元组关系演算(TRC)](https://www.geeksforgeeks.org/dbms-tupple-relational-calculus/)
2.  [领域关系演算(DRC)](https://www.geeksforgeeks.org/dbms-domain-relational-calculus/)

关系演算表示为:

```
{ t | P(t) }

Where,
t: the set of tuples
p: is the condition which is true for the given set of tuples.
```

**关系代数与关系演算的区别:**

<center>

| S.NO | 关系代数 | 关系微积分 |
| 1. | 这是一种过程语言。 | 而关系演算是声明性语言。 |
| 2. | 关系代数意味着如何获得结果。 | 而关系演算意味着我们必须获得什么结果。 |
| 3. | 在关系代数中，指定了操作必须执行的顺序。 | 而在关系演算中，顺序是不指定的。 |
| 4. | 关系代数与领域无关。 | 而关系演算可以是领域相关的。 |
| 5. | 关系代数更接近编程语言。 | 而关系演算并没有更接近编程语言。 |

</center>