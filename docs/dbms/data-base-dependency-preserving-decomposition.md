# 数据库管理系统|依赖保持分解

> 原文:[https://www . geeksforgeeks . org/data-base-dependency-preserving-decomposition/](https://www.geeksforgeeks.org/data-base-dependency-preserving-decomposition/)

**依赖关系保存**

分解 D = { R1，R2，R3。R 的 Rn }是一组函数依赖的依赖保持，如果

```
(F1 ∪ F2 ∪ … ∪ Fm)+ = F+.
Consider a relation R
R ---> F{...with some functional dependency(FD)....}

R is decomposed or divided into R1 with FD { f1 } and R2 with { f2 }, then
there can be three cases:

f1 U f2 = F -----> Decomposition is dependency preserving. 
f1 U f2 is a subset of F -----> Not Dependency preserving.
f1 U f2 is a super set of F -----> This case is not possible.
```

**问题:**设一个关系 R (A，B，C，D)和函数依赖{ AB–>C，C–>D，D–>A }。关系 R 分解为 R1( A，B，C)和 R2(C，D)。检查分解是否保持依赖关系。
T3】解决方案:

```
R1(A, B, C) and R2(C, D)

Let us find closure of F1 and F2
To find closure of F1, consider all combination of
ABC. i.e., find closure of A, B, C, AB, BC and AC
Note ABC is not considered as it is always ABC 

closure(A) = { A }  // Trivial
closure(B) = { B }  // Trivial
closure(C) = {C, A, D} but D can't be in closure as D is not present R1.
           = {C, A}
C--> A   // Removing C from right side as it is trivial attribute

closure(AB) = {A, B, C, D}
            = {A, B, C}
AB --> C  // Removing AB from right side as these are trivial attributes

closure(BC) = {B, C, D, A}
            = {A, B, C}
BC --> A  // Removing BC from right side as these are trivial attributes

closure(AC) = {A, C, D}
AC --> D  // Removing AC from right side as these are trivial attributes             

F1 {C--> A, AB --> C, BC --> A}.
Similarly F2 { C--> D }

In the original Relation Dependency { AB --> C , C --> D , D --> A}.
AB --> C is present in F1.
C --> D is present in F2.
D --> A is not preserved.

F1 U F2 is a subset of F. So given decomposition is not dependency preservingg.
```

**问题 1:**
让 R (A，B，C，D)是一个具有以下函数依赖关系的关系模式:

```
A → B, B → C,
C → D and D → B. 

The decomposition of R into 
(A, B), (B, C), (B, D)

```

**(A)** 给出无损连接，是依赖保持
**(B)** 给出无损连接，但不是依赖保持
**(C)** 没有给出无损连接，而是依赖保持
**(D)** 没有给出无损连接，不是依赖保持

解决方法参见[本](https://www.geeksforgeeks.org/gate-gate-it-2008-question-59/)。

**问题 2**
R(A、B、C、D)是关系。以下哪一项没有无损连接、保持依赖性的 BCNF 分解？
(A) A- > B，B- > CD
(B) A- > B，B- > C，C- > D
(C) AB- > C，C- > AD
(D) A - > BCD

解决方法参见[本](https://www.geeksforgeeks.org/gate-gate-cs-2001-question-48/)。

以下是前一年 GATE 问题的测验。

[https://www . geesforgeks . org/DBMS-GQ/database-design-normal-forms-GQ/](https://www.geeksforgeeks.org/dbms-gq/database-design-normal-forms-gq/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论