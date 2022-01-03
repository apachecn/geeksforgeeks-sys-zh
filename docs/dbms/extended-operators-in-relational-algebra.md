# 关系代数中的扩展算子

> 原文:[https://www . geesforgeks . org/extended-operator-in-relational-代数/](https://www.geeksforgeeks.org/extended-operators-in-relational-algebra/)

关系代数中关系模型和基本算子的基本思想:

[关系模型](https://www.geeksforgeeks.org/relational-model-in-dbms/)

[关系代数中的基本算子](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/)

扩展运算符是那些可以从基本运算符派生出来的运算符。关系代数中主要有三种类型的扩展运算符:

*   **加入**
*   **路口**
*   **划分**

用于理解扩展运算符的关系是 STUDENT、STUDENT_SPORTS、ALL_SPORTS 和 EMPLOYEE，分别如表 1、表 2、表 3 和表 4 所示。

**学生**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

**表 1**

**学生 _ 体育**

| **滚动 _ 否** | **运动** |
| one | 羽毛球 |
| Two | 板球 |
| Two | 羽毛球 |
| four | 羽毛球 |

**表 2**

**ALL_SPORTS**

| **运动** |
| 羽毛球 |
| 板球 |

**表 3**

**员工**

| **电磁脉冲 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| five | 纳瑞许 | 相信我 | Nine billion seven hundred and eighty-two million nine hundred and eighteen thousand one hundred and ninety-two | Twenty-two |
| six | 斯威塔 | RANCHI | Nine billion eight hundred and fifty-two million six hundred and seventeen thousand six hundred and twenty-one | Twenty-one |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

**表 4**

***交集(∩):*** 两个关系上的交集 R1 和 R2 只有在 R1 和 R2 是**并集兼容**的情况下才能计算(这两个关系应该具有相同数量的属性，并且两个关系中对应的属性具有相同的域)。交集运算符应用于两个关系时，如 R1 **∩** R2 将给出一个与 R1 和 R2 元组的关系。语法:

```
 Relation1 ∩ Relation2
```

```
Example: Find a person who is student as well as employee-  STUDENT ∩ EMPLOYEE 
```

根据基本运算符(联合和减) :

```
STUDENT ∩ EMPLOYEE = STUDENT + EMPLOYEE - (STUDENT U EMPLOYEE) 
```

**结果:**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

***条件 Join(⋈ <sub>c</sub> ) :*** 条件连接是当你想基于某些条件连接两个或多个关系时使用的。示例:选择员工人数大于员工人数的学生

```
STUDENT*⋈<sub>c</sub>*<sub>STUDENT.ROLL_NO>EMPLOYEE.EMP_NO</sub>EMPLOYEE
```

在基本操作符方面(交叉积和选择) :

```
σ <sub>(STUDENT.ROLL_NO>EMPLOYEE.EMP_NO)</sub>(STUDENT×EMPLOYEE)
```

**结果:**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **电磁脉冲 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |

***equijoin(⋈):***等价连接是条件连接的**特例，其中一对属性之间只存在相等条件。由于相等连接的结果中两个属性的值相等，因此结果中将只出现一个属性。**

示例:选择“员工人数”等于“员工人数”的学生

```
STUDENT⋈<sub>STUDENT.ROLL_NO=EMPLOYEE.EMP_NO</sub>EMPLOYEE
```

在基本算子方面(叉积、选择和投影) :

```
∏<sub>(STUDENT.ROLL_NO, STUDENT.NAME, STUDENT.ADDRESS, STUDENT.PHONE, STUDENT.AGE EMPLOYEE.NAME, EMPLOYEE.ADDRESS, EMPLOYEE.PHONE, EMPLOYEE>AGE)</sub>(σ <sub>(STUDENT.ROLL_NO=EMPLOYEE.EMP_NO)</sub> (STUDENT×EMPLOYEE))
```

结果:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

***自然 Join(⋈):*** 这是一种等价连接的特殊情况，其中等式条件适用于关系 r 和 s(应用连接操作的关系)中具有相同名称的所有属性。在对两个关系应用自然连接时，不需要显式编写相等条件。自然连接也将只返回相似的属性一次，因为它们的值在结果关系中是相同的。

示例:选择“滚动编号”等于“学生体育”的“滚动编号”的学生如下:

```
STUDENT⋈STUDENT_SPORTS
```

在基本算子方面(叉积、选择和投影) :

```
∏<sub>(STUDENT.ROLL_NO, STUDENT.NAME, STUDENT.ADDRESS, STUDENT.PHONE, STUDENT.AGE STUDENT_SPORTS.SPORTS)</sub>(σ <sub>(STUDENT.ROLL_NO=STUDENT_SPORTS.ROLL_NO)</sub> (STUDENT×STUDENT_SPORTS))
```

**结果:**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **运动** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | 羽毛球 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | 板球 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | 羽毛球 |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | 羽毛球 |

默认情况下，自然连接是内部连接，因为不满足连接条件的元组不会出现在结果集中。例如:在 STUDENT 中具有 ROLL_NO 3 的元组与 STUDENT_SPORTS 中的任何元组都不匹配，因此它不是结果集的一部分。

***左外 Join(⟕):*** 在两个关系 r 和 s 上应用联接时，r 或 s 的一些元组没有出现在不满足联接条件的结果集中。但是左外连接给出了结果集中 R 的所有元组。不满足连接条件的 R 元组的 s 属性的值为空

示例:选择员工的“员工编号”大于“员工编号”的学生，以及其他学生的详细信息

```
STUDENT&#10197<sub>STUDENT.ROLL_NO>EMPLOYEE.EMP_NO</sub>EMPLOYEE
```

**结果**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **电磁脉冲 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | 空 | 空 | 空 | 空 | 空 |

***右外 Join(⟖):*** 在两个关系 r 和 s 上应用连接时，r 或 s 的一些元组不会出现在不满足连接条件的结果集中。但是右外连接给出了结果集中所有的元组。不满足连接条件的元组的值为空

例如:选择员工的“员工编号”大于“员工编号”的学生，以及其他员工的详细信息

```
STUDENT⟖<sub>STUDENT.ROLL_NO>EMPLOYEE.EMP_NO</sub>EMPLOYEE
```

**结果:**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **电磁脉冲 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| 空 | 空 | 空 | 空 | 空 | five | 纳瑞许 | 相信我 | Nine billion seven hundred and eighty-two million nine hundred and eighteen thousand one hundred and ninety-two | Twenty-two |
| 空 | 空 | 空 | 空 | 空 | six | 斯威塔 | RANCHI | Nine billion eight hundred and fifty-two million six hundred and seventeen thousand six hundred and twenty-one | Twenty-one |
| 空 | 空 | 空 | 空 | 空 | four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

***全外 Join(⟗):*** 在两个关系 r 和 s 上应用连接时，r 或 s 的一些元组不会出现在不满足连接条件的结果集中。但是全外连接给出了结果集中 S 的所有元组和 R 的所有元组。不满足连接条件的 S 的元组对于 R 的属性将具有空值，反之亦然。

例如:选择员工的“员工编号”大于“员工编号”的学生，以及其他员工和其他学生的详细信息

```
STUDENT⟗<sub>STUDENT.ROLL_NO>EMPLOYEE.EMP_NO</sub>EMPLOYEE
```

**结果:**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **电磁脉冲 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| 空 | 空 | 空 | 空 | 空 | five | 纳瑞许 | 相信我 | Nine billion seven hundred and eighty-two million nine hundred and eighteen thousand one hundred and ninety-two | Twenty-two |
| 空 | 空 | 空 | 空 | 空 | six | 斯威塔 | RANCHI | Nine billion eight hundred and fifty-two million six hundred and seventeen thousand six hundred and twenty-one | Twenty-one |
| 空 | 空 | 空 | 空 | 空 | four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | 空 | 空 | 空 | 空 | 空 |

***分部运算符(÷):*** 分部运算符 A**B 可以应用，如果且仅当:**

*   **乙的属性是甲的属性的适当子集**
*   **除法运算符返回的关系将具有属性=(A 的所有属性–B 的所有属性)**
*   **除法运算符返回的关系将返回关系 A 中与每个 B 的元组相关联的那些元组。**

**考虑上面表 2 和表 3 中给出的学生体育和全民体育的关系。**

**将除法运算符应用为**

```
 **STUDENT_SPORTS÷ ALL_SPORTS**
```

*   **该操作有效，因为 ALL_SPORTS 中的属性是 STUDENT_SPORTS 中属性的适当子集。**
*   **结果关系中的属性将具有属性{滚动 _ 否，运动}-{运动} =滚动 _ 否**
*   **结果关系中的元组将具有与所有 B 的元组{羽毛球，板球}相关联的 ROLL_NO。ROLL_NO 1 和 4 仅与羽毛球相关。ROLL_NO 2 与 b 的所有元组相关联。因此得到的关系将是:**

| **滚动 _ 否** |
| Two |

* * *

**[关系代数运算符概述](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)**

**前一年的入门问题**

**[https://www . geesforgeks . org/gate-gate-cs-2012-question-50/](https://www.geeksforgeeks.org/gate-gate-cs-2012-question-50/)
T3】https://www . geesforgeks . org/gate-gate-cs-2012-question-43/**

**Sonal Tuteja 撰写的文章。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论**