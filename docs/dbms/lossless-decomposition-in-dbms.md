# 数据库管理系统中的无损分解

> 原文:[https://www . geeksforgeeks . org/无损-在 dbms 中分解/](https://www.geeksforgeeks.org/lossless-decomposition-in-dbms/)

无损连接分解是将关系 R 分解成关系 R1、R2，这样，如果我们执行关系 R1 和 R2 的自然连接，它将返回原始关系 R。这在删除数据库冗余的同时保留原始数据方面是有效的…

换句话说，通过无损分解，使用连接从分解的表 R1 和 R2 重建关系变得可行。

在无损分解中，我们选择公共属性，选择公共属性的标准是公共属性必须是关系 R1、R2 或两者的候选键或超级键。

如果下列函数依赖中至少有一个在 F+(函数依赖的闭包)
中，将关系 R 分解成 R1 和 R2 是无损连接分解

```

R1 ∩ R2 → R1
   OR
R1 ∩ R2 → R2
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

参见[本](https://www.geeksforgeeks.org/gate-gate-it-2008-question-59/)了解解决方案。

**问题 2**
R(A，B，C，D)是关系。以下哪一项没有无损连接、保持依赖性的 BCNF 分解？
(A) A- > B，B- > CD
(B) A- > B，B- > C，C- > D
(C) AB- > C，C- > AD
(D) A - > BCD

参见[本](https://www.geeksforgeeks.org/gate-gate-cs-2001-question-48/)了解解决方案。

以下是前一年 GATE 问题的测验

[https://www . geesforgeks . org/DBMS-GQ/database-design-normal-forms-GQ/](https://www.geeksforgeeks.org/dbms-gq/database-design-normal-forms-gq/)

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息