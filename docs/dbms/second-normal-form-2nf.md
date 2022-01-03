# 第二范式(2NF)

> 原文:[https://www.geeksforgeeks.org/second-normal-form-2nf/](https://www.geeksforgeeks.org/second-normal-form-2nf/)

[第一范式(1NF)](https://www.geeksforgeeks.org/first-normal-form-1nf/) 并没有消除冗余，而是消除了重复组。

不是在一个记录中有多列相同类型的数据，(0NF 或未规范化的形式)，而是将重复的信息移除到一个单独的关系中，并将它们表示为行。这就是 1NF 的构成。

**第二范式(2NF):**
第二范式(2NF)基于全功能依赖的概念。第二范式适用于具有复合键的关系，即具有由两个或多个属性组成的主键的关系。具有单属性主键的关系自动至少为 2NF。不在 2NF 中的关系可能会受到更新异常的影响。

要处于第二范式，关系必须处于第一范式，并且关系不能包含任何部分依赖。如果一个关系没有部分依赖关系，即没有非主属性(不属于任何候选关键字的属性)依赖于表中任何候选关键字的任何适当子集，则该关系为 2NF。

换句话说，

> 处于第一范式并且每个非主键属性在功能上都完全依赖于主键的关系，则该关系处于第二范式(2NF)。

**注–**如果候选键的合适子集确定非素属性，则称为[部分依赖](https://practice.geeksforgeeks.org/problems/differentiate-between-full-functional-dependency-and-partial-dependency)。

1NF 到 2NF 关系的[正常化](https://www.geeksforgeeks.org/database-normalization-normal-forms/)包括**去除部分依赖**。如果存在部分依赖，我们通过将部分依赖属性与它们的行列式副本放在一个新的关系中，从关系中移除部分依赖属性。

考虑下面给出的例子。

**例-1:**
考虑下表。

```
STUD_NO            COURSE_NO        COURSE_FEE
1                     C1                  1000
2                     C2                  1500
1                     C4                  2000
4                     C3                  1000
4                     C1                  1000
2                     C5                  2000

```

{请注意，有许多课程的学费相同。}

这里，
COURSE_FEE 不能单独决定 COURSE_NO 或 STUD_NO 的值；
课程 _ 费用和学习编号不能决定课程 _ 编号的值；
课程费和课程号不能决定学习号的价值；
因此，
课程 _ 费用将是一个非质数属性，因为它不属于唯一的候选关键字{梭哈 _ 否，课程 _ 否}；
但是，COURSE_NO - > COURSE_FEE，即 COURSE_FEE 依赖于 COURSE_NO，它是候选关键字的适当子集。非质数属性 COURSE_FEE 依赖于候选关键字的一个适当子集，这是一个部分依赖，因此这种关系不在 2NF 中。

要将上述关系转换为 2NF，
我们需要将该表拆分为两个表，如:
表 1: STUD_NO，COURSE_NO
表 2: COURSE_NO，COURSE_FEE

```
       Table 1                                    Table 2
STUD_NO            COURSE_NO          COURSE_NO                COURSE_FEE     
1                 C1                  C1                        1000
2                 C2                  C2                        1500
1                 C4                  C3                        1000
4                 C3                  C4                        2000
4                 C1                  C5                        2000        
2                 C5                         

```

**注意–**2NF 试图减少存储在内存中的冗余数据。例如，如果有 100 名学生参加 C1 课程，我们不需要将所有 100 条记录的费用存储为 1000，而是可以将它存储在第二个表中，因为 C1 的课程费用为 1000。

**示例-2:**
考虑以下与 R (A，B，C，D)相关的函数依赖关系

```
AB -> C  [A and B together determine C]
BC -> D  [B and C together determine D]
```

在上述关系中，AB 是唯一的候选键，不存在部分依赖关系，即 AB 的任何适当子集都不确定任何非素数属性。