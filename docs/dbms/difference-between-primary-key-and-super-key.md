# 主键和超级键的区别

> 原文:[https://www . geeksforgeeks . org/主键和超级键的区别/](https://www.geeksforgeeks.org/difference-between-primary-key-and-super-key/)

先决条件–[关系模型中的键](https://www.geeksforgeeks.org/dbms-keys-candidate-super-primary-alternate-and-foreign/)
**1。超级键:**
超级键是一个属性(或一组属性)，用于唯一标识关系中的所有属性。所有超级键不能都是候选键，但它的反例是真的。在关系中，超级键的数量多于候选键的数量。

**示例:**
我们有一个给定的关系 R(A，B，C，D，E，F)，我们将通过以下给定的依赖关系来检查是否是超级键:

```
Functional dependencies         Super key
AB->CDEF                         YES
CD->ABEF                         YES
CB->DF                           NO
D->BC                            NO 
```

通过使用键 **AB** 我们可以识别表格的其余属性 **(CDEF)** 。同样关键**光盘。**但是，使用 **CB** 键，我们只能识别 **D** 和 **F** 而不能识别 **A** 和 **E** 。同理键 **D** 。

**2。主键:**
候选键是唯一标识关系或表中元组的一组属性(或属性)。关系中可以有多个候选键，从中可以选择一个作为主键。

**示例:**

```
Student{Stud_No, Stud_name, Stud_phone, 
             Stud_state, Stud_country, Stud_age} 
```

这里我们可以看到两个候选键 **Stud_No** 和 **Stud_phone。**可以选择 STUD_No 作为主键(多个候选键中只有一个)。

**超级键和主键的区别:**

| S.NO | 超级钥匙 | 主关键字 |
| 1. | 超级键是用于唯一标识关系中所有属性的属性(或属性集)。 | 主键是用于唯一标识关系中所有属性的最小属性集(或属性集)。 |
| 2. | 所有超级键不能都是主键。 | 主键是最小超级键。 |
| 3. | 各种超级键一起构成了选择候选键的标准。 | 我们可以选择任何最小候选键作为主键。 |
| 4. | 在关系中，超级键的数量多于主键的数量。 | 而在关系中，主键的数量少于超级键的数量。 |
| 5. | 超级键的属性可以包含空值。 | 主键的属性不能包含空值。 |