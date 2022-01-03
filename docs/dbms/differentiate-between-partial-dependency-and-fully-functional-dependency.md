# 区分部分依赖和完全功能依赖

> 原文:[https://www . geesforgeks . org/区分部分依赖和完全功能依赖/](https://www.geeksforgeeks.org/differentiate-between-partial-dependency-and-fully-functional-dependency/)

**全功能依赖:**
如果 X 和 Y 是关系的属性集，则 Y 是全功能依赖 X，如果 Y 是功能依赖 X 但不依赖 X 的任何适当子集。
**例–**
在关系 ABC- > D 中，属性 D 是全功能依赖 ABC 而不依赖 ABC 的任何适当子集。这意味着像 AB、BC、A、B 等 ABC 的子集不能确定 d
让我们再举一个例子–

**供应表**

<figure class="table">

| **供应商 _id** | **项目 _id** | **价格** |
| one | one | Five hundred and forty |
| Two | one | Five hundred and forty-five |
| one | Two | Two hundred |
| Two | Two | Two hundred and one |
| one | one | Five hundred and forty |
| Two | Two | Two hundred and one |
| three | one | Five hundred and forty-two |

从表中，我们可以清楚地看到，supplier_id 和 item_id 都不能唯一地确定价格，但是 supplier_id 和 item_id 可以一起确定价格。所以我们可以说价格在功能上完全依赖于{ supplier_id，item_id }。这总结并给出了我们的全功能依赖关系

```
{ supplier_id , item_id } -> price
```

**部分功能依赖:**
功能依赖 X- > Y 是部分依赖如果 Y 是功能依赖 X，Y 可以由 X 的任意适当子集确定
例如，我们有关系 AC- > B，A- > D，D- > B.
现在如果我们计算{A <sup>+</sup> }的闭包=ADB
这里只有 A 能够确定 B，这意味着 B 部分依赖 AC。
我们再举一个例子–

**学生表**

<figure class="table">

| **名称** | **滚动 _ 号** | **球场** |
| 拉维河 | Two | 数据库管理系统 |
| 定时（timing 的缩写） | three | 操作系统（Operating System） |
| 约翰 | five | Java 语言(一种计算机语言，尤用于创建网站) |

在这里，我们可以看到属性名称和 roll_no 都能够唯一地标识一个课程。因此，我们可以说这种关系是部分依赖的。

## **完全功能依赖和部分功能依赖的区别:**

<figure class="table">

|   | 

**全功能依赖**

 | 

**部分功能依赖**

 |
| --- | --- | --- |
| 1. | 如果 Y 在功能上依赖于 X，而 Y 在功能上不依赖于 X 的任何适当子集，则函数依赖 X->Y 是完全函数依赖 | 函数依赖 X->Y 是部分依赖，如果 Y 函数依赖 X，Y 可以由 X 的任何适当子集确定 |
| 2. | 在完全函数依赖中，非质数属性在函数上依赖于候选键。 | 在部分函数依赖中，非质数属性在函数上依赖于候选键的一部分。 |
| 3. | 在全功能依赖中，如果我们去掉 X 的任何属性，那么依赖将不再存在。 | 在部分函数依赖中，如果我们去掉 X 的任何属性，那么依赖仍然会存在。 |
| 4. | 完全函数依赖相当于第二范式的规范化标准。 | 部分函数依赖不等于第二范式的规范化标准。相反，2NF 消除了部分依赖。 |
| 5. | 如果一个属性 A 在功能上依赖于另一个属性 B，而不是依赖于该属性的任何部分(子集)，则该属性 A 在功能上完全依赖于该属性 B。 | 如果属性 A 在功能上依赖于该属性的任何部分(子集)，则该属性 A 在功能上部分依赖于其他属性 B。 |
| 6. | 函数依赖提高了数据库中数据的质量。 | 部分依赖不会提高数据质量。为了在第二范式中归一化，它必须被消除。 |

</figure>

</figure>

</figure>