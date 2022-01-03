# 无损和有损连接分解的区别

> 原文:[https://www . geesforgeks . org/无损和有损连接分解之间的差异/](https://www.geeksforgeeks.org/difference-between-lossless-and-lossy-join-decomposition/)

将关系分解成更小的子关系的过程称为分解。[在 DBMS 中需要分解](https://www.geeksforgeeks.org/properties-of-relational-decomposition/)来将一个关系转换成特定的范式，这进一步减少了关系中的冗余、异常和不一致性。

数据库管理系统中主要有两种类型的分解-

1.  [无损分解](https://www.geeksforgeeks.org/lossless-decomposition-in-dbms/)
2.  有损分解

**无损和有损连接分解的区别:**

<figure class="table">

| 无损的 | 有电能损耗的 |
| --- | --- |
| 如果原始关系 R 存在自然连接，则关系模式 R 的 R1、R2、R2…Rn 分解被称为无损分解 | 如果有自然连接导致与原始关系 R 的无关元组相加，则关系模式 R 的分解 R1、R2、R2…Rn 被称为有损分解 |
| 形式上，设 R 是一个关系，R1，R2，R3 … Rn 是它的分解，分解是无损的，如果–

```
 R1 ⨝ R2 ⨝ R3 .... ⨝ Rn = R
```

 | 形式上，设 R 是一个关系，R1，R2，R3 … Rn 是它的分解，分解是有损的，如果–

```
 R ⊂ R1 ⨝ R2 ⨝ R3 .... ⨝ Rn
```

 |
| 由于在分解的自然连接之后获得的关系等同于原始关系，因此不会丢失信息。因此，它也被称为非加法连接分解 | 在分解的自然连接之后，由于无关元组被添加到关系中，因此会丢失信息。因此，它也被称为粗心分解。 |
| 子关系的公共属性是任何一个关系的超键。 | 子关系的公共属性不是任何子关系的超键。 |

**示例-1:**
示例检查给定分解是否无损连接分解。

假设有一个关系模式 R(A，B，C)。R1(甲，乙)和 R2(乙，丙)是它的分解。

<figure class="table">

| A | B | C |
| --- | --- | --- |
| 第一等的 | b1 | c1 |
| 主动脉第二声 | b1 | c1 |
| 第一等的 | b2 | c2 |

<figure class="table">

| B | C |
| --- | --- |
| b1 | c1 |
| b1 | c1 |
| b2 | c2 |

</figure>

为了无损分解，

```
R1 ⨝ R2 = R then, R1 ⨝ R2  is
```

<figure class="table">

| A | B | C |
| --- | --- | --- |
| 第一等的 | b1 | c1 |
| 主动脉第二声 | b1 | c1 |
| 第一等的 | b2 | c2 |

</figure>

```
As, R1 ⨝ R2 = R, 
```

这种分解是无损的。

**示例-2:**
示例检查给定分解是否有损连接分解。

假设有一个关系模式 R(A，B，C)。R1(甲，乙)和 R2(甲，丙)是它的分解。

<figure class="table">

| A | B | C |
| --- | --- | --- |
| 第一等的 | b1 | c1 |
| 主动脉第二声 | b1 | c1 |
| 第一等的 | b2 | c2 |
| 第一等的 | b3 | c3 |

<figure class="table">

| A | B |
| --- | --- |
| 第一等的 | b1 |
| 主动脉第二声 | b1 |
| 第一等的 | b2 |
| 第一等的 | b3 |

</figure>

<figure class="table">

| A | C |
| --- | --- |
| 第一等的 | c1 |
| 主动脉第二声 | c1 |
| 第一等的 | c2 |
| 第一等的 | c3 |

</figure>

现在分解是有损耗的，

```
R ⊂ R1 ⨝ R2 then, R1 ⨝ R2  is
```

<figure class="table">

| A | B | C |
| --- | --- | --- |
| 第一等的 | b1 | c1 |
| 第一等的 | b1 | c2 |
| 主动脉第二声 | b1 | c1 |
| 第一等的 | b2 | c2 |
| 第一等的 | b2 | c1 |
| 第一等的 | b3 | c3 |
| 第一等的 | b3 | c1 |

</figure>

```
As, R ⊂ R1 ⨝ R2, 
```

这种分解是有损耗的。
因此，我们可以知道分解是无损的还是有损的。

</figure>

</figure>

</figure>