# 关系模型中的键类型(候选、超级、主要、替代和外来)

> 原文:[https://www . geesforgeks . org/type-key-in-relational-model-候选者-super-primary-alternate-and-foreign/](https://www.geeksforgeeks.org/types-of-keys-in-relational-model-candidate-super-primary-alternate-and-foreign/)

我们强烈建议将下面的帖子作为先决条件。

[DBMS |关系模型介绍和 Codd 规则](https://www.geeksforgeeks.org/introduction-of-relational-model-and-codd-rules-in-dbms/)

**关系模型中不同类型的键**

![image](img/997ee46433bdacefb3606f6eb0fafe3d.png)

**候选关键字:**能够唯一识别元组的最小属性集被称为候选关键字。例如，学生关系中的学习编号。

*   候选关键字的值对于每个元组都是唯一且非空的。
*   一个关系中可以有多个候选键。例如，STUD_NO 是关系 STUDENT 的候选键。
*   候选键可以是简单的(只有一个属性)，也可以是复合的。例如，{STUD_NO，COURSE_NO}是关系 STUDENT_COURSE 的复合候选键。
*   关系中的候选键的数量是 nC(楼层(n/2))，例如，如果一个关系有 5 个属性，即 R(A，B，C，D，E)，那么候选键的总数是 5C(楼层(5/2))=10。

**注意–**在 SQL Server 中，一个具有可空列的唯一约束，**只允许**在该列**中的值“**空**”一次**。这就是为什么在这里，STUD_PHONE 属性是一个候选属性，但不能是主键属性中的“null”值。

**超级密钥:**能够唯一识别元组的属性集称为超级密钥。例如，螺柱 _ 编号，(螺柱 _ 编号，螺柱 _ 名称)等。

*   向候选关键字添加零个或多个属性会生成超级关键字。
*   候选键是一个超级键，但反之则不是。

**主键:**关系中可以有多个候选键，从中可以选择一个作为主键。例如，STUD_NO 和 STUD_PHONE 都是关系 STUDENT 的候选键，但是 STUD_NO 可以被选为主键(在许多候选键中只有一个)。

**备用密钥:**主键以外的候选密钥称为备用密钥。例如，STUD_NO 和 STUD_PHONE 都是关系 STUDENT 的候选键，但是 STUD_PHONE 将是备用键(许多候选键中只有一个)。

**外键:**如果一个属性只能取其他属性的值，那么它将是它所引用的属性的外键。被引用的关系称为被引用关系，对应的属性称为被引用属性，引用被引用关系的关系称为引用关系，对应的属性称为引用属性。被引用关系的被引用属性应该是它的主键。例如，学生课程中的学习编号是学生关系中学习编号的外键。

值得注意的是，与任何给定关系的主键不同，外键可以为空，也可以包含重复的元组，即它不需要遵循唯一性约束。

例如，学生课程关系中的学习编号不是唯一的。已经对第一和第三元组重复了该过程。但是，STUDENT 关系中的 STUD_NO 是一个主键，它需要总是唯一的，并且不能为空。

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息