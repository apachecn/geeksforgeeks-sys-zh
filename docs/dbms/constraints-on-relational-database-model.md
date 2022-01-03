# 关系数据库模型的约束

> 原文:[https://www . geesforgeks . org/constraints-on-relational-database-model/](https://www.geeksforgeeks.org/constraints-on-relational-database-model/)

在建模[关系数据库](https://www.geeksforgeeks.org/introduction-of-relational-model-and-codd-rules-in-dbms/)的设计时，我们可以设置一些限制，比如允许在关系中插入什么值，允许在关系中进行什么样的修改和删除。这些是我们对关系数据库施加的限制。

在像 ER 模型这样的模型中，我们没有这样的特性。

数据库中的约束可以分为三大类:

1.  数据模型中应用的约束称为**隐式约束**。
2.  通过在 [DDL(数据定义语言)](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/)中指定直接应用于数据模型模式的约束。这些被称为**基于模式的约束或显式约束**。
3.  不能直接应用于数据模型架构的约束。我们称这些为基于应用的或语义约束。

所以这里我们将处理**隐式约束**。

关系数据库的约束主要有 4 种类型:

1.  域约束
2.  关键制约因素
3.  实体完整性约束
4.  引用完整性约束

让我们详细讨论以上每个约束。

**1。领域限制:**

1.  每个域都必须包含原子值(最小的不可分割单元)，这意味着不允许复合和多值属性。
2.  我们在这里执行数据类型检查，这意味着当我们给一个列分配一个数据类型时，我们限制它可以包含的值。如果我们将属性年龄的数据类型指定为 int，我们就不能给它除了 int 数据类型之外的值。

**例:**
![\begin{center} \begin{tabular}{ |c|c|c|c| } \hline EID & Name & Phone \\ \hline \001 & Bikash Dutta & 123456789 \\ & & 234456678\\ \hline \end{tabular} \end{center}       ](img/53cf10bec0bd3cbbfb0c8d5da7c1eb5c.png "Rendered by QuickLaTeX.com")

**说明:**
在上述关系中，Name 是复合属性，Phone 是多值属性，因此违反了域约束。

**2。关键约束或唯一性约束:**

1.  这些被称为唯一性约束，因为它确保关系中的每个元组都应该是唯一的。
2.  一个关系可以有多个键或候选键(最小超键)，从中我们选择其中一个键作为主键，我们对从候选键中选择主键没有任何限制，但建议选择属性数量较少的候选键。
3.  主键中不允许空值，因此非空约束也是键约束的一部分。

**例:**
![\begin{center} \begin{tabular}{ |c|c|c|c| } \hline EID & Name & Phone \\ \hline \001 & Bikash & 6000000009 \\ \002 & Paul & 9000090009\\ \001 & Tuhin & 9234567892\\ \hline \end{tabular} \end{center}       ](img/05da03a63f55a60d66226ddc8a9fd016.png "Rendered by QuickLaTeX.com")

**说明:**
在上表中，EID 是主键，第一个和最后一个元组在 EID ie 01 中具有相同的值，因此违反了键约束。

**3。实体完整性约束:**

1.  实体完整性约束表示没有主键可以取空值，因为使用主键我们可以唯一地标识关系中的每个元组。

**例:**
![\begin{center} \begin{tabular}{ |c|c|c|c| } \hline EID & Name & Phone \\ \hline \001 & Bikash & 9000900099 \\ \002 & Paul & 600000009\\ NULL & Sony & 9234567892\\ \hline \end{tabular} \end{center}       ](img/38cf782d503be5ed0f8f38b08e94b7d8.png "Rendered by QuickLaTeX.com")

**说明:**
在上面的关系中，EID 被设为主键，主键不能取 null 值，但是在第三元组中，主键为 NULL，所以是违反 Entity Integrity 约束的。

**4。参照完整性约束:**

1.  引用完整性约束在两个关系或表之间指定，用于维护两个关系中元组之间的一致性。
2.  这个约束通过外键来实施，当关系 R1 的外键中的一个属性与关系 R2 的主键具有相同的域时，则 R1 的外键被称为引用或参照关系 R2 的主键。
3.  关系 R1 元组中的外键值可以采用关系 R2 中某个元组的主键值，也可以采用空值，但不能为空。

**例:**
![\begin{center} \begin{tabular}{ |c|c|c|c| } \hline EID & Name & DNO \\ \hline \001 & Divine & 12 \\ \002 & Dino & 22\\ \004 & Vivian & 14\\ \hline \end{tabular} \end{center}       ](img/804c693937213c6753ab530a0c4062fa.png "Rendered by QuickLaTeX.com")

![\begin{center} \begin{tabular}{ |c|c|c|c| } \hline DNO & Place \\ \hline \112 & Jaipur \\ \113 & Mumbai \\ \114 & Delhi \\ \hline \end{tabular} \end{center}       ](img/9ebbecddce554972b68e43ad9f6e2095.png "Rendered by QuickLaTeX.com")

**说明:**
上图中，第一关系的 DNO 是外键，第二关系的 DNO 是主键。第一个表的外键中不允许 DNO = 22，因为第二个关系的主键中没有定义 DNO = 22
。因此，这里违反了参照完整性约束