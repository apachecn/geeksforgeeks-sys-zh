# DBMS 中的领域关系演算

> 原文:[https://www . geesforgeks . org/domain-relational-演算-in-dbms/](https://www.geeksforgeeks.org/domain-relational-calculus-in-dbms/)

**领域关系演算**是一种非过程查询语言，在能力上等同于元组关系演算。领域关系演算只提供查询的描述，但不提供解决方法。在领域关系演算中，查询被表示为，

```
{ < x1, x2, x3, ..., xn > | P (x1, x2, x3, ..., xn ) } 
```

其中，< x <sub>1</sub> ，x <sub>2</sub> ，x <sub>3</sub> ，…，x <sub>n</sub> >代表结果域变量，P (x <sub>1</sub> ，x <sub>2</sub> ，x <sub>3</sub> ，…，x <sub>n</sub> 代表等价于谓词演算的条件或公式。

**谓词演算公式:**

1.  所有比较运算符的集合
2.  一组连接词，像 and，or，not
3.  量词集

**示例:**

**表-1:客户**

| 用户姓名 | 街道 | 城市 |
| --- | --- | --- |
| 德伯特 | 卡达姆塔拉 | Alipurduar |
| 萨彦坦 | 乌代布尔 | 俾路支省 |
| 苏蜜亚 | Nutanchati | 班库拉 |
| Ritu | 南 | 孟买 |

**表-2:借款**

| 贷款号 | 分行名称 | 数量 |
| --- | --- | --- |
| L01 | 主要的 | Two hundred |
| L03 | 主要的 | One hundred and fifty |
| L10 | 潜水艇 | Ninety |
| L08 | 主要的 | Sixty |

**表-3:借款人**

| 用户姓名 | 贷款号 |
| --- | --- |
| Ritu | L01 |
| 德伯特 | L08 |
| 苏蜜亚 | L03 |

**查询-1:** 查找大于等于 100 金额的贷款号、分行、贷款金额。

```
{≺l, b, a≻ | ≺l, b, a≻ ∈ loan ∧ (a ≥ 100)}
```

结果关系:

| 贷款号 | 分行名称 | 数量 |
| --- | --- | --- |
| L01 | 主要的 | Two hundred |
| L03 | 主要的 | One hundred and fifty |

**查询-2:** 查找金额大于等于 150 的每笔贷款的贷款号。

```
{≺l≻ | ∃ b, a (≺l, b, a≻ ∈ loan ∧ (a ≥ 150)}
```

结果关系:

| 贷款号 |
| --- |
| L01 |
| L03 |

**查询-3:** 找到所有在“主”支行有贷款的客户的名字，找到贷款金额。

```
{≺c, a≻ | ∃ l (≺c, l≻ ∈ borrower ∧ ∃ b (≺l, b, a≻ ∈ loan ∧ (b = “Main”)))}
```

结果关系:

| 用户姓名 | 数量 |
| --- | --- |
| Ritu | Two hundred |
| 德伯特 | Sixty |
| 苏蜜亚 | One hundred and fifty |

**注意:**
将出现在结果关系中的域变量必须出现在|≺和≻之前，并且所有域变量必须按照它们在原始关系或表中的顺序出现。