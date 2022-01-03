# 演绎数据库中的条款形式

> 原文:[https://www . geeksforgeeks . org/clausal-in-form-in-演绎数据库/](https://www.geeksforgeeks.org/clausal-form-in-deductive-databases/)

在**分句形式**中，公式由多个分句组成，其中每个**分句**由多个*字面量*组成，仅通过 OR 逻辑连接词连接。

一个公式可以有以下*量词*:

1.  **通用量词–**
    可以理解为–“对于所有的 x，P(x)成立”，意思是 P(x)对于宇宙中的每个物体 x 都成立。
    例:所有卡车都有轮子。

2.  **存在量词–**
    可以理解为–“存在一个 x 使得 P(x)”，意思是 P(x)对于宇宙中至少一个物体 x 是真的。
    例:有人关心你。

一个**从句形式**的公式必须转化为另一个具有以下特征的公式:

*   All variables in the formula are universally quantified. Hence, it is not necessary to include the universal quantifiers explicitly for all. The quantifiers are removed, and all variables in the formula are implicitly quantified by the universal quantifier. 
*   因为公式是由许多子句组成的，并且每个子句都是由许多仅通过或逻辑连接词连接的文字组成的。因此，每个子句都是文字的*析取*。

*   为了形成一个公式，子句本身仅由“与”逻辑连接词连接。因此，公式的从句形式是从句的*连词*。

任何公式都可以转换成从句形式。

**示例:**
文字可以是正文字，也可以是负文字。对于每个都是文字析取的单个子句的形式。对于条款形式:

```
NOT(P1) *OR* NOT(P2) *OR* ..... *OR* NOT(Pn) *OR* Q1 *OR* Q2 *OR* ..... *OR* Qm 
```

上面的子句有 **n** 负文字量和 **m** 正文字量。该子句可转换为以下等效逻辑公式:

```
P1 *AND* P2 *AND* ..... *AND* Pn => Q1 *OR* Q2 *OR* ..... *OR* Qm 
```

其中“= >”是隐含符号。

如果所有的 p 字面值(i = 1，2，…)都为真，那么第二个公式只有在至少一个 Q 为真时才为真，这就是(隐含)符号的含义。对于第一个公式，如果所有的 P 字面值(i = 1，2，…，n)都为真，则它们的否定都为假；所以在这种情况下，只有至少有一个 Q 是真的，它才是真的。

因此，上述两个公式是等价的，因此它们的真值总是相同的。