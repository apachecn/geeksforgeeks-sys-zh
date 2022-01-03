# 关系代数中的基本算子

> 原文:[https://www . geesforgeks . org/basic-operator-in-relational-代数-2/](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/)

关系模型基础:[关系模型](https://www.geeksforgeeks.org/relational-model-in-dbms/)

关系代数是一种过程查询语言，它将关系作为输入，并将关系作为输出返回。有一些基本的运算符可以应用于关系，以产生我们将逐一讨论的所需结果。我们将使用表 1、表 2 和表 3 中分别给出的 STUDENT_SPORTS、EMPLOYEE 和 STUDENT 关系来理解各种运算符。

**表 1: STUDENT_SPORTS**

<figure class="table">

| **滚动 _ 否** | **运动** |
| one | 羽毛球 |
| Two | 板球 |
| Two | 羽毛球 |
| four | 羽毛球 |

**表 2:员工**

<figure class="table">

| **电磁脉冲 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| five | 纳瑞许 | 相信我 | Nine billion seven hundred and eighty-two million nine hundred and eighteen thousand one hundred and ninety-two | Twenty-two |
| six | 斯威塔 | RANCHI | Nine billion eight hundred and fifty-two million six hundred and seventeen thousand six hundred and twenty-one | Twenty-one |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

</figure>

**表 3:学生**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

***选择算子(σ):*** 选择算子用于根据某种条件从关系中选择元组。语法:

```
σ <sub>(Cond)(Relation Name)</sub>
```

从表 3 给出的学生关系中提取年龄大于 18 岁的学生

```
σ <sub>(AGE>18)(STUDENT)</sub>
```

**结果:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |

***投影算子(∏):*** 投影算子用于投影关系中的特定列。语法:

```
∏<sub>(Column 1,Column 2….Column n)(Relation Name)</sub>
```

从表 3 给出的学生关系中提取卷号和名称

```
∏<sub>(ROLL_NO,NAME)(STUDENT)</sub>
```

**结果:**

<figure class="table">

| **滚动 _ 否** | **名称** |
| one | 随机存取存储 |
| Two | RAMESH |
| three | SUJIT |
| four | SURESH |

**注意:**如果投影后的结果关系有重复行，则删除。例如:∏ <sub>(地址)</sub>(学生)将删除一个值为德里的重复行，并返回三行。

***叉积(X):*** 叉积用于连接两个关系。对于关系 1 的每一行，关系 2 的每一行都是串联的。如果关系 1 有 m 个元组，并且关系 2 有 n 个元组，那么关系 1 和关系 2 的叉积将有 m×n 个元组。语法:

```
Relation1 X Relation2
```

要对表 1 中给出的学生关系和表 2 中给出的学生体育关系应用叉积，

```
STUDENT X STUDENT_SPORTS
```

**结果:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **滚动 _ 否** | **运动** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | one | 羽毛球 |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | Two | 板球 |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | Two | 羽毛球 |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | four | 羽毛球 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | one | 羽毛球 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | Two | 板球 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | Two | 羽毛球 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | four | 羽毛球 |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | one | 羽毛球 |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | Two | 板球 |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | Two | 羽毛球 |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | four | 羽毛球 |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | one | 羽毛球 |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | Two | 板球 |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | Two | 羽毛球 |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | four | 羽毛球 |

***并集(U):*** 两个关系上的并集 R1 和 R2 只有在 R1 和 R2 是**并集兼容**的情况下才能计算(这两个关系应该有相同数量的属性，并且两个关系中对应的属性有相同的域)。当联合运算符应用于两个关系时，R1 和 R2 将给出一个与位于 R1 或 R2 的元组的关系。R1 和 R2 的元组在结果关系中只出现一次。语法:

```
 Relation1 U Relation2
```

查找学生或员工，我们可以使用联合运算符，如:

```
STUDENT U EMPLOYEE
```

**结果:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |
| five | 纳瑞许 | 相信我 | Nine billion seven hundred and eighty-two million nine hundred and eighteen thousand one hundred and ninety-two | Twenty-two |
| six | 斯威塔 | RANCHI | Nine billion eight hundred and fifty-two million six hundred and seventeen thousand six hundred and twenty-one | Twenty-one |

***减(-):*** 减只有在 R1 和 R2 是**联盟兼容**的情况下，才能计算出 R1 和 R2 的两个关系。当负运算符应用于两个关系(如 R1-R2)时，将给出一个与 R1 但不在 R2 的元组的关系。语法:

```
 Relation1 - Relation2
```

找到学生而不是员工，我们可以使用负运算符，如:

```
STUDENT - EMPLOYEE
```

**结果:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |

***Rename(ρ):***Rename 运算符用于给关系赋予另一个名称。语法:

```
ρ(Relation2, Relation1)
```

要将学生关系重命名为学生 ENT1，我们可以使用重命名操作符，如:

```
ρ(STUDENT1, STUDENT)
```

如果您想创建一个学生姓名与学生姓名的关系，可以使用重命名操作符:

```
ρ(STUDENT_NAMES, ∏<sub>(ROLL_NO, NAME)(STUDENT))</sub>
```

[扩展关系代数运算符](https://www.geeksforgeeks.org/extended-operators-in-relational-algebra/) [关系代数运算符概述](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)

往年门题
[https://www . geesforgeks . org/Gate-Gate-cs-2012-question-50/](https://www.geeksforgeeks.org/gate-gate-cs-2012-question-50/)
[https://www . geesforgeks . org/Gate-Gate-cs-2012-question-43/](https://www.geeksforgeeks.org/gate-gate-cs-2012-question-43/)

Sonal Tuteja 撰写的文章。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>