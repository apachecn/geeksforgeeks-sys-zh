# 元组关系演算(TRC)和域关系演算(DRC)的区别

> 原文:[https://www . geesforgeks . org/tuple-relational-演算-TRC-和-domain-relational-演算-drc/](https://www.geeksforgeeks.org/difference-between-tuple-relational-calculus-trc-and-domain-relational-calculus-drc/)

**1。[元组关系演算(TRC)](https://www.geeksforgeeks.org/tuple-relational-calculus-trc-in-dbms/) :**
元组关系演算是一种非过程查询语言，它指定选择关系中的元组。它可以选择值范围内的元组或某些属性值的元组等。生成的关系可以有一个或多个元组。

```
Notation :
{T | P (T)}   or {T | Condition (T)}  
```

-其中 T 是结果元组，P(T)是用于获取 T 的条件

**示例:**

```
{T | EMPLOYEE (T) AND T.DEPT_ID = 10} 
```

这将选择在第 10 部门工作的所有员工姓名元组。

**2。[域关系演算(DRC)](https://www.geeksforgeeks.org/domain-relational-calculus-in-dbms/) :**
域关系演算使用基于条件从关系中选择的属性列表。它与 TRC 相同，但不同之处在于选择属性而不是选择整个元组。

```
Notation :
{ a1, a2, a3, ..., an | P (a1, a2, a3, ..., an) } 
```

-其中 a1、a2、a3、… an 是关系的属性，P 是条件。

**示例:**

```
{ |  < EMPLOYEE > DEPT_ID = 10 } 
```

选择在第 10 部门工作的员工的员工标识和员工姓名。

**元组关系演算(TRC)和域关系演算(DRC)的区别:**

<center>

| 元组关系演算 | 领域关系演算 |
| --- | --- |
| 在 TRS，变量代表来自特定关系的元组。 | 在 DRS 中，变量表示从指定域中提取的值。 |
| 元组是关系的单个元素。在数据库术语中，它是一行。 | 域相当于列数据类型和对数据值的任何约束。 |
| 在这个过滤变量中使用关系元组。 | 在这种情况下，过滤是基于属性域进行的。 |
| 符号:
{T &#124; P (T)}或{T &#124;条件(T)} | 符号:
{ a1，a2，a3，…，an &#124; P (a1，a2，a3，…，an)} |
| 示例:
{T &#124; EMPLOYEE (T)和 T.DEPT_ID = 10} | 示例:
{ &#124; <员工> DEPT_ID = 10 } |

</center>