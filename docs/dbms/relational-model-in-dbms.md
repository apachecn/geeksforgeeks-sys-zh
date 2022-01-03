# 数据库管理系统中的关系模型

> 原文:[https://www.geeksforgeeks.org/relational-model-in-dbms/](https://www.geeksforgeeks.org/relational-model-in-dbms/)

关系模型是由 E.F. Codd 提出的，用来以关系或表格的形式对数据进行建模。在使用 er 图设计数据库的概念模型后，我们需要将概念模型转换为关系模型，该关系模型可以使用任何关系数据库管理系统语言实现，如 Oracle SQL、MySQL 等。所以我们将看到什么是关系模型。

**什么是关系模型？**

关系模型表示数据如何存储在关系数据库中。关系数据库以关系(表)的形式存储数据。考虑一个属性为 ROLL_NO、姓名、地址、电话和年龄的关系学生，如表 1 所示。

**学生**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
| four | SURESH | 德里 |   | Eighteen |

</figure>

**重要术语**

*   **属性:**属性是定义关系的属性。例如:**卷号**，**名称**
*   **关系模式:**关系模式用属性表示关系的名称。例如:学生是学生的关系模式。如果一个模式有一个以上的关系，它被称为关系模式。
*   **元组:**关系中的每一行都称为元组。上述关系包含 4 个元组，其中一个元组如下所示:

<figure class="table">

| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |

</figure>

*   **关系实例:**在特定时间实例的关系元组集称为关系实例。表 1 显示了学生在特定时间的关系实例。只要数据库中有插入、删除或更新，它就会改变。
*   **度:**关系中属性的个数称为关系的度。上面定义的**学生**关系为 5 级。
*   **基数:**关系中元组的数量称为基数。上面定义的**学生**关系的基数为 4。
*   **列:**列表示特定属性的一组值。 **ROLL_NO** 一栏摘自关系学生。

<figure class="table">

| **滚动 _ 否** |
| one |
| Two |
| three |
| four |

</figure>

*   **空值:**未知或不可用的值称为空值。它由空格表示。例如:有 4 号卷的学生的电话为空。

**关系模型中的约束**

在设计关系模型时，我们定义了数据库中存在的数据必须满足的一些条件，称为约束。在数据库中执行任何操作(插入、删除和更新)之前，都会检查这些约束。如果违反了任何约束，操作将失败。

**域约束:**这些是属性级约束。属性只能取域范围内的值。例如，；如果对学生关系应用约束年龄> 0，插入年龄的负值将导致失败。

**密钥完整性:**数据库中的每个关系都应该至少有一组属性，唯一地定义一个元组。这些属性集被称为密钥。例如:学生卷号是一个关键。没有两个学生可以有相同的学号。所以密钥有两个属性:

*   对于所有元组，它应该是唯一的。
*   它不能有空值。

**参照完整性:**当一个关系的一个属性只能从同一关系或任何其他关系的其他属性取值时，称为参照完整性。让我们假设我们有两个关系

**学生**T2】

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** | **分支代码** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen | 特许测量员 |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen | 特许测量员 |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty | 欧洲经济委员会 |
| four | SURESH | 德里 |   | Eighteen | 信息技术 |

**分支**

<figure class="table">

| **分支代码** | 分支名称 |
| cs | 计算机科学 |
| **IT** | 信息技术 |
| **ECE** | 电子与通信工程 |
| **CV** | 土木工程 |

</figure>

学生的分支代码只能取分支的分支代码中存在的值，称为参照完整性约束。引用其他关系的关系称为引用关系(在本例中为学生)，其他关系引用的关系称为引用关系(在本例中为分支)。

**异常**

异常是不规则的，或偏离预期或正常状态的东西。在设计数据库时，我们识别三种异常:插入、更新和删除。

**引用关系中的插入异常:**

如果引用属性值中不存在引用属性值，则不能在 REFERENCING REFERENCE 中插入行。例如:在学生关系中插入分支代码为“我”的学生将导致错误，因为“我”不在分支的分支代码中。

**引用关系中的删除/更新异常:**

如果在 REFERENCED ATTRIBUTE 的值中使用了 REFERENCED ATTRIBUTE 的值，则不能从 REFERENCE REFERENCE 中删除或更新行。例如；如果我们试图从具有 BRANCH_CODE 'CS '的 BRANCH 中删除元组，将导致错误，因为' CS '被 STUDENT 的 BRANCH_CODE 引用，但是如果我们试图从具有 BRANCH_CODE CV 的 BRANCH 中删除该行，它将被删除，因为该值没有被引用关系使用。可以通过以下方法处理:

**ON DELETE CASCADE:** 如果从 REFERENCED relationship 中删除了 REFERENCING ATTRIBUTE 使用的值，则将从 REFERENCED relationship 中删除元组。例如；，如果我们用分支代码“CS”从分支中删除一行，那么与分支代码 CS(在这种情况下是 ROLL_NO 1 和 2)相关的 STUDENT 行将被删除。

**更新级联:**如果引用关系中引用属性使用的属性值被更新，它将更新引用关系中的引用属性。例如；，如果我们将一行从分支代码为“CS”的分支更新为“CSE”，那么与分支代码为“CS”的学生相关的行(在本例中为 ROLL_NO 1 和 2)将被分支代码为“CSE”的分支更新。

**SUPER KEYS:**
任何允许我们在给定关系中识别唯一行(元组)的属性集都被称为 SUPER KEYS。从这些超级键中，我们总能从中选择一个合适的子集作为主键。这种键被称为候选键。如果有两个或多个属性的组合被用作主键，那么我们称之为复合键。

[关系代数中的基本算子](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/)
文章由 Sonal Tuteja 供稿。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息