# 演绎数据库中小句形式和喇叭小句形式的区别

> 原文:[https://www . geeksforgeeks . org/clause-form-and-horn-clause-form-in-演绎数据库/](https://www.geeksforgeeks.org/difference-between-clausal-form-and-horn-clausal-form-in-deductive-database/)

**1。[分句形式](https://www.geeksforgeeks.org/clausal-form-in-deductive-databases/) :**
在这种形式中，公式由多个分句组成，其中每个分句由多个仅由或逻辑连接词连接的文字组成。

一个**从句形式**的公式必须转化为另一个具有以下特征的公式:

*   公式中的所有变量都被普遍量化。因此，没有必要明确包括所有的通用量词。量词被移除，公式中的所有变量都被通用量词隐式量化。
*   因为公式是由许多子句组成的，并且每个子句都是由许多仅通过或逻辑连接词连接的文字组成的。因此，每个子句都是文字的分解。
*   为了形成一个公式，子句本身仅由“与”逻辑连接词连接。因此，公式的从句形式是从句的连词。

**2。 [Horn 从句形式](https://www.geeksforgeeks.org/horn-clauses-in-deductive-databases/):**
Horn 从句是一个分句(字面量的析取)，最多有一个正的，也就是不必要的字面量。一个含有最多一个正的(不加修饰的)字面量的从句叫做 Horn 从句。

**喇叭条款类型:**

*   **定分句/严格喇叭分句:**正好有一个正字面。
*   **单位子句:**没有负文字的定子句。
*   **目标从句:**不带正字面的 Horn 从句。

**举例:**
**从句形式:**
文字可以是正文字也可以是负文字。对于每个都是文字析取的单个子句的形式。对于条款形式:

```
NOT(P1) OR NOT(P2) OR ..... OR NOT(Pn) OR Q1 OR Q2 OR ..... OR Qm

```

上面的子句有 n 个负文本和 m 个正文本。该子句可以转换为以下等效逻辑公式:

```
P1 AND P2 AND ..... AND Pn => Q1 OR Q2 OR ..... OR Qm

```

其中“= >”是隐含符号。

**喇叭小句形式:**

**(一)**霍恩条款，

```
NOT(P1) OR NOT(P2) OR ... OR NOT(Pn) OR Q

```

可以转化为从句:

P1 和 P2 和…和 Pn => Q

它按照以下规则写入数据日志。

```
Q :- P1, P2, ..., Pn.

```

因此，上述数据记录规则是霍恩条款。

**意思:**如果谓词 P1 和 P2 以及……和 Pn 对于它们的变量参数的特定绑定都是真的，那么 Q 也是真的，因此可以推断。

**(ii)** 霍恩条款，

```
NOT(P1) OR NOT(P2) OR ... OR NOT (Pn)

```

可以转化成

P1 和 P2 和…和 Pn =>
写入数据日志如下:

```
P1, P2, ..., Pn.

```

上面的 Datalog 表达式可以被认为是一个完整性约束，其中所有谓词必须为真才能满足查询。