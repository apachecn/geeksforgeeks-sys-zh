# 关系代数中的 RENAME (ρ)运算

> 原文:[https://www . geesforgeks . org/rename-operation-in-relational-代数/](https://www.geeksforgeeks.org/rename-operation-in-relational-algebra/)

先决条件–[在 DBMS 中介绍关系代数](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)，[关系代数中的基本运算符](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/)

RENAME 操作用于重命名关系的输出。

有时，打破一个复杂的操作序列，并将其重命名为具有不同名称的关系是简单而合适的。重命名关系的原因有很多，例如–

*   我们可能希望将关系代数表达式的结果保存为关系，以便以后使用。
*   我们可能希望将一个关系与其自身连接起来，在这种情况下，指定我们正在讨论的是哪一个表会变得过于混乱，在这种情况下，我们重命名其中一个表并对它们执行连接操作。

**符号:**

```
ρ <sub>X</sub> (R)

```

其中符号“ρ”用于表示 RENAME 运算符，R 是以名称 x 保存的操作或表达式序列的结果

*   **示例-1:** 查询将关系学生重命名为男学生，并将学生的属性–roll no，Sname 重命名为(Sno，Name)。

<figure class="table">

| Sno | 名字 |
| --- | --- |
| Two thousand six hundred | 罗尼 |
| Two thousand six hundred and fifty-five | 王侯 |

</figure>

```
ρ <sub>MaleStudent(Sno, Name)</sub> π<sub>RollNo, SName</sub>(σ<sub>Condition</sub>(Student))

```

*   **示例-2:** 查询将表部门的属性名称、年龄重命名为 A、b

```
ρ <sub>(A, B)</sub> (Department)

```

*   **示例-3:** 查询将表名 Project 重命名为 Pro，将其属性重命名为 P、Q、r

```
ρ <sub>Pro(P, Q, R)</sub> (Project)

```

*   **示例-4:** 查询将属性为 A、B、C 的表 Student 的第一个属性重命名为 p

```
ρ <sub>(P, B, C)</sub> (Student)
```