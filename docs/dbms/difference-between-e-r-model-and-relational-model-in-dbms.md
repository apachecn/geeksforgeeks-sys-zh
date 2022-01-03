# 数据库管理系统中 E-R 模型和关系模型的区别

> 原文:[https://www . geeksforgeeks . org/e-r-model-and-relational-model-in-DBMS/](https://www.geeksforgeeks.org/difference-between-e-r-model-and-relational-model-in-dbms/)

E-R 模型和关系模型是数据库管理系统中存在的两种数据模型。让我们简单了解一下它们:

**1。 [E-R 模型](https://www.geeksforgeeks.org/introduction-of-er-model/) :**
E-R 模型代表实体-关系模型。ER 模型用于从数据角度对系统的逻辑视图进行建模，该模型由以下组件组成:实体、实体类型、实体集。

一个实体可能是一个有实体存在的物体——一个特定的人、车、房子或雇员——或者它可能是一个有概念存在的物体——一个公司、一份工作或一门大学课程。实体是实体类型的对象，所有实体的集合称为实体集。例如:E1 是一个具有实体类型学生的实体，所有学生的集合称为实体集。

实体类型定义了相似实体的集合，所有实体的集合称为实体集。

**2。[关系模型](https://www.geeksforgeeks.org/relational-model-in-dbms/) :**
关系模型是由 E.F. Codd 提出的以关系或表格的形式对数据进行建模的模型。在使用 er 图设计数据库的概念模型后，我们需要将概念模型转换为关系模型，该关系模型可以使用任何关系数据库管理系统语言实现，如 Oracle SQL、MySQL 等。

考虑一个属性为 ROLL_NO、姓名、地址、电话和年龄的关系学生，如表 1 所示。

<center>
**STUDENT**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
| four | SURESH | 德里 |  | Eighteen |

</center>

让我们看看 ER 模型和关系模型的区别:

<center>

| 没有。 | 电流变模型 | 关系模型 |
| --- | --- | --- |
| 1. | ER 模型是高级或概念模型。 | 它是代表性或实现模型。 |
| 2. | 它被不知道数据库是如何实现的人使用。 | 它被程序员使用。 |
| 3. | 它表示实体的集合并描述它们之间的关系。 | 它以表格的形式表示数据，并描述它们之间的关系。 | 4. | 它由实体、实体类型、实体集等组件组成。 | 它由域、属性、元组等组件组成。 | 5. | 理解实体之间的关系很容易。 | 导出不同表之间的关系不太容易。 | 6. | 它描述基数。 | 它没有描述基数。 |

</center>