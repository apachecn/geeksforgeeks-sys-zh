# 第三范式(3NF)

> 原文:[https://www.geeksforgeeks.org/third-normal-form-3nf/](https://www.geeksforgeeks.org/third-normal-form-3nf/)

虽然[第二范式(2NF)](https://www.geeksforgeeks.org/second-normal-form-2nf/) 关系的冗余比 1NF 中的少，但它们仍可能遭受更新异常。如果我们只更新一个元组而不更新另一个元组，数据库将处于不一致的状态。这种更新异常是由可传递依赖关系引起的。我们需要通过前进到第三范式(3NF)来移除这种依赖。

**第三范式(3NF):**
关系处于第三范式，如果对非素属性不存在传递依赖，它也处于第二范式。

如果每个非平凡函数依赖项 X–> Y 中至少有一个以下条件成立，则关系为 3NF:

1.  x 是一把超级钥匙。
2.  Y 是一个主要属性(Y 的每个元素都是某个候选键的一部分)。

换句话说，

> 一种处于第一和第二范式的关系，其中没有非主键属性过渡依赖于主键，则它处于第三范式(3NF)。

**注意–**如果 A- > B and B- > C 是两个 FD，那么 A- > C 被称为传递依赖。

2NF 关系到 3NF 的[规范化](https://www.geeksforgeeks.org/database-normalization-normal-forms/)涉及到可传递依赖的移除。如果存在可传递依赖，我们通过将属性和行列式的副本放入新的关系中，从关系中移除可传递依赖的属性。

考虑下面给出的例子。

**示例-1:**
关于表 4 中给出的学生，

![](img/930cd4d87f43e604e6412c5061401e0b.png)

功能描述集:
{螺柱 _ 编号- >螺柱 _ 名称，螺柱 _ 编号- >螺柱 _ 状态，螺柱 _ 状态- >螺柱 _ 国家，螺柱 _ 编号- >螺柱 _ 年龄}

候选键:
{螺柱 _ 否}

对于表 4 中的这个关系，螺柱 _ 编号->螺柱 _ 状态和螺柱 _ 状态->螺柱 _ 国家为真。所以 STUD_COUNTRY 是过渡依赖于 STUD_NO 的，它违反了第三范式。为了将其转换为第三范式，我们将关系 STUDENT (STUD_NO，STUD_NAME，STUD_PHONE，STUD_STATE，STUD_COUNTRY_STUD_AGE)分解为:

```
STUDENT (STUD_NO, STUD_NAME, STUD_PHONE, STUD_STATE, STUD_AGE) 
STATE_COUNTRY (STATE, COUNTRY) 
```

**例-2:**
考虑关系 R(A，B，C，D，E)

```
A -> BC,
CD -> E, 
B -> D, 
E -> A 
```

上述关系中所有可能的候选键都是{A，E，CD，BC}所有属性都在右边，所有函数依赖项都是质数。

**注意–**
第三范式(3NF)被认为*对于正常的关系数据库设计是足够的*，因为大多数 3NF 表没有插入、更新和删除异常。此外，3NF *始终确保功能依赖保持和无损*。