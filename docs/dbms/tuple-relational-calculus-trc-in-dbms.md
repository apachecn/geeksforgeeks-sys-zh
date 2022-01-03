# 数据库管理系统中的元组关系演算

> 原文:[https://www . geesforgeks . org/tuple-relational-calculation-TRC-in-DBMS/](https://www.geeksforgeeks.org/tuple-relational-calculus-trc-in-dbms/)

元组关系演算是一种**非过程查询语言**，不同于关系代数。元组演算只提供查询的描述，但不提供解决方法。因此，它解释了该做什么，而不是怎么做。
在元组演算中，查询表示为

```
{t| P(t)}
```

其中 t =结果元组，
P(t) =称为谓词，这些是用于获取 t 的条件

因此，它生成所有元组 t 的集合，使得谓词 P(t)对于 t 是真的

P(t)可以有各种条件与 OR(∩)、AND(∩)、NOT()逻辑组合。
它还使用量词:
∃t∈r(Q(t))=“t 中存在”一个与 r 相关的元组，因此谓词 q(t)为真。
对于关系 r 中的“所有”元组，∀ t ∈ r (Q(t)) = Q(t)为真。

**示例:**
**表-1:客户**

<figure class="table">

| 用户姓名 | 街道 | 城市 |
| --- | --- | --- |
| 索伦布 | A7 | 帕蒂拉 |
| 梅哈克 | B6 | 贾朗达尔 |
| 苏米提 | D9 | 卢迪亚纳 |
| 河口 | A5 号 | 帕蒂拉 |

**表-2:分公司**

<figure class="table">

| 分行名称 | 分支城市 |
| --- | --- |
| 字母表 | 帕蒂拉 |
| 极好的 | 卢迪亚纳 |
| 全球健康倡议 | 贾朗达尔 |

**表-3:账户**

<figure class="table">

| 账号 | 分行名称 | 保持平衡 |   |
| --- | --- | --- | --- |
| One thousand one hundred and eleven | 字母表 | Fifty thousand |   |
| One thousand one hundred and twelve | 极好的 | ten thousand |   |
| One thousand one hundred and thirteen | 全球健康倡议 | Nine thousand |   |
| One thousand one hundred and fourteen | 字母表 | Seven thousand |   |

**表-4:借款**

<figure class="table">

| 贷款号 | 分行名称 | 数量 |
| --- | --- | --- |
| L33 | 字母表 | ten thousand |
| L35 | 极好的 | Fifteen thousand |
| L49 | 全球健康倡议 | Nine thousand |
| L98 | 极好的 | Sixty-five thousand |

**表-5:借款人**

<figure class="table">

| 用户姓名 | 贷款号 |
| --- | --- |
| 索伦布 | L33 |
| 梅哈克 | L49 |
| 河口 | L98 |

**表-6:存款人**

<figure class="table">

| 用户姓名 | 账号 |
| --- | --- |
| 索伦布 | One thousand one hundred and eleven |
| 梅哈克 | One thousand one hundred and thirteen |
| 苏米提 | One thousand one hundred and fourteen |

**查询-1:** 查找大于等于 10000 金额的贷款号、分行、贷款金额。

```
{t| t ∈ loan  ∧ t[amount]>=10000}
```

结果关系:

<figure class="table">

| 贷款号 | 分行名称 | 数量 |
| --- | --- | --- |
| L33 | 字母表 | ten thousand |
| L35 | 极好的 | Fifteen thousand |
| L98 | 极好的 | Sixty-five thousand |

</figure>

在上面的查询中，t[amount]被称为元组变量。

**查询-2:** 查找金额大于等于 10000 的每笔贷款的贷款号。

```
{t| ∃ s ∈ loan(t[loan number] = s[loan number]  
                   ∧ s[amount]>=10000)}
```

结果关系:

<figure class="table">

| 贷款号 |
| --- |
| L33 |
| L35 |
| L98 |

**查询-3:** 查找所有在银行有贷款和账户的客户的姓名。

```
{t | ∃ s ∈ borrower( t[customer-name] = s[customer-name])   
     ∧  ∃ u ∈ depositor( t[customer-name] = u[customer-name])}
```

结果关系:

<figure class="table">

| 用户姓名 |
| --- |
| 索伦布 |
| 梅哈克 |

**查询-4:** 查找所有在“农行”分行贷款的客户名称。

```
{t | ∃ s ∈ borrower(t[customer-name] = s[customer-name]  
   ∧ ∃ u ∈  loan(u[branch-name] = “ABC” ∧ u[loan-number] = s[loan-number]))}
```

结果关系:

<figure class="table">

| 用户姓名 |
| --- |
| 索伦布 |

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>