# 关系分解的性质

> 原文:[https://www . geesforgeks . org/properties-of-relational-decomposition/](https://www.geeksforgeeks.org/properties-of-relational-decomposition/)

当关系模型中的关系不是合适的范式时，就需要分解关系。在数据库中，将表分解成多个表称为分解。关系分解的属性如下所示:

1.  **Attribute Preservation:**
    Using functional dependencies the algorithms decompose the universal relation schema R in a set of relation schemas D = { R1, R2, ….. Rn } relational database schema, where ‘D’ is called the Decomposition of R.

    R 中的属性将出现在分解中的至少一个关系模式 Ri 中，即没有属性丢失。这称为分解的*属性保存*条件。

2.  **[依赖关系保持](https://www.geeksforgeeks.org/data-base-dependency-preserving-decomposition/) :**
    如果在 F 中指定的每个功能依赖关系 X- > Y 直接出现在分解 D 中的关系模式 Ri 之一中，或者可以从出现在某些 Ri 中的依赖关系中推断出来。这是*依赖保存*。

如果分解不是依赖保持，那么在分解中会丢失一些依赖。要检查这个条件，在分解中取两个或更多关系的 JOIN。

例如:

```
R = (A, B, C)
F = {A ->B, B->C}
Key = {A}

R is not in BCNF.
Decomposition R1 = (A, B), R2 = (B, C) 
```

R1 和 R2 在 BCNF，无损连接分解，依赖保持。
F 中指定的每个函数依赖项要么直接出现在分解中的一个关系中。
关系 R 的所有依赖关系不一定都出现在某个关系 R1 中。
所有关系 R1 上的依赖的并集等价于 r 上的依赖就足够了

9.  **Non Additive Join Property:**
    Another property of decomposition is that D should possess is the *Non Additive Join Property*, which ensures that no spurious tuples are generated when a NATURAL JOIN operation is applied to the relations resulting from the decomposition.
10.  **No redundancy:**
    Decomposition is used to eliminate some of the problems of bad design like anomalies, inconsistencies, and redundancy.If the relation has no proper decomposition, then it may lead to problems like loss of information.
11.  **[Lossless Join](https://www.geeksforgeeks.org/lossless-decomposition-in-dbms/):**
    Lossless join property is a feature of decomposition supported by normalization. It is the ability to ensure that any instance of the original relation can be identified from corresponding instances in the smaller relations.

    例如:
    R:关系，F:R 上的函数依赖集，
    X，Y:R 的分解，
    关系 R 的分解{R1，R2，…，Rn}如果 R1，R2，…，Rn 的自然连接恰好产生关系 R，则称为 R 的无损分解。

    如果我们可以恢复，分解是无损的:
    R(A，B，C) - >分解- > R1(A，B) R2(A，C) - >恢复- > R'(A，B，C)
    因此，R' = R
    分解是无损的如果:
    X 交集 Y - > X，即:X 和 Y 共有的所有属性在功能上决定了 X 中的所有属性。
    X 交集 Y - > Y， 即:X 和 Y 两者共有的所有属性在功能上决定了 Y 中的所有属性
    如果 X 交集 Y 形成 X 或 Y 的超键，则 R 的分解是无损分解。