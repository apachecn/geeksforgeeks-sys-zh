# 常见的 DBMS 面试问题

> 原文:[https://www . geesforgeks . org/common-question-DBMS-interview-questions/](https://www.geeksforgeeks.org/commonly-asked-dbms-interview-questions/)

**1。与传统的基于文件的系统相比，DBMS 有什么优势？**

开发数据库管理系统是为了解决传统操作系统支持的典型 Fille 处理系统的以下困难。
1。数据冗余和不一致性
2。数据访问困难
3。数据隔离–多个文件和格式
4。诚信问题
5。更新的原子性
6。多用户并发访问
7。安全问题

**2。什么是超级、初级、候选**、**和外键？**
一个[超级键](https://www.geeksforgeeks.org/difference-between-super-key-and-candidate-key/)是一个关系模式的一组属性，该模式的所有属性在功能上都依赖于该属性。没有两行可以具有相同的超级键属性值。
一个[候选关键字](https://www.geeksforgeeks.org/difference-between-super-key-and-candidate-key/)是一个最小超关键字，也就是说，没有合适的候选关键字属性子集可以是超关键字。
A [主键](https://www.geeksforgeeks.org/difference-between-primary-and-candidate-key/)是候选键之一。其中一个候选键被选为最重要的，并成为主键。一个表中不能有多个主键..
一个**外键**是一个表中唯一标识另一个表的一行的字段(或字段集合)。

**3。主键和唯一约束有什么区别？**
主键不能有空值，唯一约束可以有空值。表中只有一个主键，但可以有多个唯一约束。

**4。什么是数据库规范化？**
这是一个基于给定关系模式的功能依赖和主键来分析给定关系模式的过程，以实现以下期望的属性:
1。最小化冗余
2。最小化插入、删除和更新异常不满足属性的关系模式被分解为满足所需属性的较小关系模式。

**5。为什么推荐使用 DBMS？通过列举它的一些主要优点来解释？**

数据库管理系统的一些主要优点如下:

*   **受控冗余:** DBMS 支持一种机制，通过将所有数据集成到单个数据库中来控制数据库内部数据的冗余，由于数据只存储在一个地方，因此不会发生数据的重复。
*   **数据共享:**由于同一数据库将在所有用户之间共享，并由不同的应用程序共享，因此也可以在数据库管理系统中同时在多个用户之间共享数据。
*   **备份和恢复工具:**通过提供“备份和恢复”功能，数据库管理系统将一次又一次创建数据备份的痛苦降至最低，该功能会自动创建数据备份，并在需要时恢复数据。
*   **完整性约束的执行:**完整性约束对数据的执行非常重要，这样在放入一些约束后的细化数据就会存储在数据库中，然后是 DBMS。
*   **数据的独立性:**简单来说就是可以在不影响任何应用程序结构的情况下，改变数据的结构。

**6。DDL、DML** 、**和 DCL 在 SQL 上有什么区别？**
下面是三个的一些细节。
**DDL** 代表数据定义语言。像 CREATE、ALTER、DROP 和 RENAME 这样的 SQL 查询就属于这一类。
**DML** 代表数据操作语言。像选择、插入和更新这样的 SQL 查询就属于这一类。
**DCL** 代表数据控制语言。像 GRANT 和 REVOKE 这样的 SQL 查询就属于这一类。

**7。having 和 where 子句有什么区别？**
HAVING 用于为 select 语句中使用的组或聚合函数指定条件。WHERE 子句在分组之前选择。HAVING 子句在分组后选择行。与 HAVING 子句不同，WHERE 子句不能包含聚合函数。(详见[本](http://newtonapples.com/difference-clause-clause/)举例)。参见 [Having vs Where 子句？](https://www.geeksforgeeks.org/having-vs-where-clause-in-sql/)了解更多详情

**8。如何打印表格中的重复行？**
参见

**9。什么是加入？**
基于两个或多个表之间的公共字段，使用一个 SQL 连接来组合两个或多个表中的数据。例如，考虑以下两个表。

**表–**学生表

<figure class="table">

| 注册编号 | 学生姓名 | 地址 |
| One thousand | 极客 1 | 极客 squiz1 |
| One thousand and one | 极客 2 | 极客 squiz2 |
| One thousand and two | 极客 3 | 极客 squiz3 |

</figure>

**表–**学生课程表

<figure class="table">

| 快跑！快跑 | 注册编号 |
| one | One thousand |
| Two | One thousand |
| three | One thousand |
| one | One thousand and two |
| Two | One thousand and three |

下面是一个连接查询，显示了注册不同课程号的学生的姓名。

```
SELECT StudentCourse.CourseID, Student.StudentName
       FROM StudentCourse
       INNER JOIN Student 
       ON StudentCourse.EnrollNo = Student.EnrollNo
       ORDER BY StudentCourse.CourseID;
```

上述查询将产生以下结果。

<figure class="table">

| 快跑！快跑 | 学生姓名 |
| one | 极客 1 |
| one | 极客 3 |
| Two | 极客 1 |
| three | 极客 1 |

**9。什么是身份？**
身份(或自动号码)是一个自动生成数值的列。可以设置起始值和增量值，但大多数数据库管理员将它们保留为 1。GUID 列也会生成数字；这个值无法控制。标识/GUID 列不需要编制索引。

**10。什么是 SQL 中的视图？如何创建视图？**
视图[视图](http://en.wikipedia.org/wiki/View_(SQL))是一个基于 SQL 语句结果集的虚拟表。我们可以使用创建视图语法来创建。

```
CREATE VIEW view_name AS
SELECT column_name(s)
FROM table_name
WHERE condition
```

**11 时。观有什么用？**
1。视图可以表示表中包含的数据的子集；因此，视图可以限制底层表对外部世界的暴露程度:给定用户可能有权查询视图，但被拒绝访问基表的其余部分。
2。视图可以将多个表连接并简化为一个虚拟表。
3。视图可以充当聚合表，数据库引擎在其中聚合数据(总和、平均值等)。)并将计算结果作为数据的一部分。
4。视图可以隐藏数据的复杂性。
5。视图占用很少的存储空间；数据库只包含视图的定义，而不是它所呈现的所有数据的副本。
6。根据所使用的 SQL 引擎，视图可以提供额外的安全性。

**12 时。什么是触发器？**
触发器是与插入、更新或删除操作相关联的代码。每当对表执行关联查询时，代码都会自动执行。触发器对于维护数据库的完整性非常有用。

**13。什么是存储过程？**
存储过程就像一个包含一组一起编译的操作的函数。它包含一组通常在应用程序中用来执行一些常见数据库任务的操作。

**14。触发器和存储过程有什么区别？**
与存储过程不同，触发器不能被直接调用。它们只能与查询相关联。

**15。什么是交易？什么是 ACID 属性？**
数据库事务是一组必须作为整体对待的数据库操作，这意味着要么执行所有操作，要么不执行任何操作。一个例子可以是从一个账户到另一个账户的银行交易。借方和贷方操作必须同时执行，否则不执行。ACID [](http://en.wikipedia.org/wiki/ACID)(原子性、一致性、隔离性、持久性)是一组保证数据库事务得到可靠处理的属性。

**16。什么是索引？**
数据库索引是一种数据结构，它以额外写入和使用更多存储空间来维护额外的数据副本为代价，提高了数据库表上数据检索操作的速度。数据只能以一种顺序存储在磁盘上。为了支持根据不同的值进行更快的访问，需要像二分搜索法那样对不同的值进行更快的搜索，为此，在表上创建索引。这些索引需要磁盘上的额外空间，但它们允许根据不同的频繁搜索值进行更快的搜索。

**17。什么是聚集索引和非聚集索引？**
聚集索引是数据物理存储在磁盘上的索引。因此，在给定的数据库表上只能创建一个聚集索引。
非聚集索引不定义数据的物理排序，而是定义逻辑排序。通常，创建的树的叶指向磁盘记录。B 树或 B+树用于此目的。

**18。什么是反规范化？**

反规范化是一种数据库优化技术，其中我们向一个或多个表中添加冗余数据。

**19。什么是 SQL 中的子句？**

SQL 中的子句是查询的一部分，它允许您筛选或自定义向您查询数据的方式。

**20。什么是活动锁？**

活锁情况可以定义为两个或多个进程响应其他进程的变化而不断重复相同的交互，而不做任何有用的工作。这些进程不处于等待状态，它们同时运行。这与死锁不同，因为在死锁中，所有进程都处于等待状态。

**21。什么是 QBE？**

逐例查询是一种可视化/图形化的方法，通过使用称为框架表的查询模板来访问数据库中的信息。它通过将示例值直接输入查询模板来表示要实现的目标。许多个人电脑的数据库系统都使用 QBE。QBE 是一个非常强大的工具，它使用户能够在不了解任何编程语言的情况下访问用户想要的信息。QBE 的查询用框架表表示。QBE 有两个明显的特点:

QBE 有二维语法:查询看起来像表格。

**22。嵌入式 SQL 中为什么需要游标？**

游标是一个对象，用于存储应用程序逐行处理的查询输出。SQL 语句对一组数据进行操作，并返回一组数据。另一方面，宿主语言程序一次运行一行。游标用于浏览嵌入式 SQL SELECT 语句返回的一组行。光标可以比作指针。

**23。DBMS 中规范化的目的是什么？**

数据库规范化是组织数据库属性的过程，以减少或消除数据冗余(数据相同但位置不同)。

**归一化目的:**

它用于从关系表中删除重复数据和数据库异常。

通过检查表中使用的新数据类型，规范化有助于减少冗余和复杂性。

将大型数据库表划分为较小的表，并使用关系将它们链接起来是很有帮助的。

它避免了重复数据或表格中没有重复组。

它减少了数据库中出现异常的机会。

**24。数据库模式和数据库状态有什么区别？**

在特定时刻存储在数据库中的信息集合称为数据库状态，而数据库的整体设计称为数据库模式。

**25。SQL 的目的是什么？**

SQL 代表结构化查询语言，其主要目的是以插入和更新/修改数据库中的数据的形式与关系数据库进行交互。

**26。解释主键和外键的概念。**

主键用于唯一标识数据库表中的记录，而外键主要用于将两个或多个表链接在一起，因为这是一个数据库表中的特定字段，是其他表的主键。

示例:有两个表-员工和部门。两者都有一个公共字段/列作为“标识”，其中标识是雇员表的主键，而这是部门表的外键。

**27。主键和唯一键的主要区别是什么？**

下面给出了几个区别:

主键和唯一键之间的主要区别在于主键永远不能有空值，而唯一键可能由空值组成。

在每个表中，只能有一个主键，而一个表中可以有多个唯一键。

**28。就 SQL 而言，子查询的概念是什么？**

子查询基本上是包含在其他查询中的查询，也可以称为在外部查询中找到的内部查询。

**29。DROP 命令的用途是什么，DROP、TRUNCATE 和 DELETE 命令有什么区别？**

DROP 命令是一个 DDL 命令，用于从数据库中删除现有的表、数据库、索引或视图。

DROP、TRUNCATE 和 DELETE 命令之间的主要区别是:

DROP 和 TRUNCATE 命令是 DDL 命令，用于从数据库中删除表，一旦表被删除，所有与表相关的特权和索引也会被删除。这两个操作不能回滚，因此只能在必要时使用。

另一方面，DELETE 命令是一个 DML 命令，它也用于从表中删除行，并且可以回滚。

**30。UNION 和 UNION ALL 的主要区别是什么？**

UNION 和 UNION ALL 用于连接两个或多个表中的数据，但是 UNION 会删除重复的行，并在合并表中的数据后选择不同的行，而 UNION ALL 不会删除重复的行，它只是从表中选择所有数据。

**31。什么是关系子查询？**

子查询也称为嵌套查询，即写在某个查询内部的查询。当对外部查询的每一行执行子查询时，它被称为相关子查询。

非相关子查询的一个例子是:

<figure class="table">

| 从环境管理计划中选择*在(从环境管理计划的部门中选择名称。EMPID = DEPT . EMPID)； |

这里，不对外部查询的每一行执行内部查询。

**32。解释数据库管理系统中的实体、实体类型和实体集？**

实体是在现实世界中独立存在的对象、场所或事物，关于它的数据可以存储在数据库中。例如，任何人、书等。

实体类型是具有相同属性的实体的集合。例如，STUDENT 表包含的行中，每一行都是一个实体，包含学生的姓名、年龄和 id 等属性，因此 STUDENT 是一个实体类型，包含具有相同属性的实体。

实体集是同一类型实体的集合。例如，公司员工的集合。

**33。数据库管理系统中有哪些不同的抽象层次？**

数据库管理系统中有三个数据抽象层次。

它们包括:

物理层:这是数据抽象的最低层，说明数据是如何存储在数据库中的。

逻辑层:这是数据抽象的下一层，它陈述了数据的类型和存储在数据库中的数据之间的关系。

视图级别:这是数据抽象中的最高级别，只显示/陈述数据库的一部分。

**34。DBMS 中存在哪些完整性规则？**

数据库管理系统中存在两个主要的完整性规则。

**实体完整性:**这说明了一个非常重要的规则，主键的值永远不能有空值。

**参照完整性:**该规则与外键相关，外键声明要么外键的值为空值，要么它应该是任何其他关系的主键。

**35。什么是数据库管理系统中的 E-R 模型？**

E-R 模型在数据库管理系统中被称为实体-关系模型，它基于实体的概念以及这些实体之间存在的关系。

**36。什么是数据库管理系统中的功能依赖？**

这基本上是一个约束，在描述关系中不同属性之间的关系时很有用。

例如:如果某个关系“R1”有两个属性为 Y 和 Z，那么这两个属性之间的函数依赖关系可以表示为 Y->Z，表示 Z 在函数上依赖于 Y

**37。什么是数据库管理系统中的 1NF？**

1NF 被称为第一范式。

这是规范化过程中最简单的形式，说明属性的域应该只有原子值。这样做的目的是删除表中存在的重复列。

**38。什么是数据库管理系统中的 2NF？**

2NF 是第二范式。

如果任何表满足以下两个条件，则称其在 2NF 中:

1NF 里有一张桌子。

据说表的每个非主键属性在功能上完全依赖于主键。

**39。什么是数据库管理系统中的 3NF？**

3NF 是第三范式。

任何满足以下两个条件的表都被称为 3NF:

一张桌子在 2NF。

一个表的每个非质数属性都被称为不依赖于该表的每个键。

**40。什么是数据库管理系统中的 BCNF？**

BCNF 是比 3NF 更严格的 Boyce Codd 范式。

如果满足以下两个条件，则称任何表在 BCNF 都存在:

3NF 里有一张桌子。

对于存在的每个函数依赖项 X->Y，X 是表的超级键。

**41。就 SQL 而言，什么是子句？**

它与 SQL 查询一起使用，根据 SQL 中的条件，按照要求获取特定的数据。这对于从整套记录中挑选选择性记录非常有帮助。

例如，有一个查询具有 WHERE 条件，或者该查询具有 HAVING 子句。

**42。如何在 SQL 中从表中获取替代记录？**

如果您想获取奇数，那么可以使用以下查询:

<figure class="table">

| 从(选择行号，从 Emp 中选择行号)中选择行号，其中 mod(行号，2)= 1； |

如果要取偶数，可以使用以下查询:

<figure class="table">

| 从(选择行号，从 Emp 中选择行号)中选择行号，其中 mod(行号，2)= 0； |

**43。SQL 中的模式匹配是如何完成的？**

答:在 LIKE 运算符的帮助下，模式匹配在 SQL 中是可能的。“%”在与 0 个或更多字符匹配时与 LIKE 运算符一起使用，而“_”用于与一个特定字符匹配。

示例:

<figure class="table">

| 从 Emp WHERE 名称中选择*如“b %”； |

<figure class="table">

| 从 Emp WHERE 名称中选择*如‘Hans _’； |

**44。什么是 SQL 中的联接？**

联接是一种 SQL 语句，用于根据两个或更多表中的公共字段/列来联接数据或行。

**45。SQL 中有哪些不同类型的连接？**

有 4 种类型的 SQL 联接:

内部连接:这种类型的连接用于从两个表中常见的表中获取数据。

左连接:这将返回位于连接左侧的表中的所有行，但仅返回位于连接右侧的表中的匹配行。

右联接:这将返回位于联接右侧的表中的所有行，但仅返回位于联接左侧的表中的匹配行。

完全联接:这将返回已设置联接条件的所有表中的行，不匹配的行保留空值。

**46。扳机是什么意思？**

触发器是非常重要的代码或程序之一，可以自动执行以响应表或视图中发生的事件。例如，如果在员工数据库中插入了一条新记录，那么相关表(如薪资表、部门表和角色表)中的数据将自动创建。

**47。解释存储过程。**

存储过程是函数形式的一组 SQL 语句，它有一个唯一的名称，存储在关系数据库管理系统(RDBMS)中，需要时可以访问。

**48。什么是 RDBMS？**

关系数据库管理系统是一个关系数据库管理系统，它以表的形式包含数据，数据是根据表中的公共字段来访问的。

**49。数据库管理系统中有哪些不同类型的关系？**

数据库管理系统中的关系描述了表之间的关联。

不同类型的关系有:

**一对一**:这基本上说明了表与表之间应该是一对一的关系，即两个表都应该有一条记录。

**一对多**:表示一个表可以有多种关系，即一个主键表只能保存一条记录，该记录在相关表中可以有多条、一条或无记录。

**多对多**:表示两个表都可以和很多其他表相关联。

**50。实体类型扩展是什么意思？**

将相似的实体类型汇编成一个特定的类型，并组合成一个实体集，这就是实体类型扩展。

**51。什么是 dbms 中的概念设计？**

概念设计是数据库设计过程的第一阶段。这个阶段的目标是设计一个独立于数据库软件和物理细节的数据库。这个过程的输出是一个概念数据模型，它描述了给定问题域的主要数据实体、属性、关系和约束。

**52。区分逻辑数据库设计和物理数据库设计。展示这种分离如何导致数据独立性。**

<figure class="table">

| **参数** | **逻辑数据库设计** | **物理数据库设计** |
| 工作 | 将概念模式(或 ER 模式)从高级数据模型映射或转换为关系数据库模式。 | 根据物理存储结构、记录放置和索引，设计了存储数据库的规范。 |
| 标准的选择 | 映射可以分两个阶段进行:

*   独立于系统的映射，但依赖于数据模型
*   根据特定的数据库管理系统定制模式

 | 以下标准通常用于指导物理数据库设计选项的选择:

*   响应时间
*   空间利用
*   交易吞吐量

 |
| 结果 | 所选数据库管理系统语言的 DDL 语句，用于指定数据库系统的概念和外部模式。但是如果 DDL 语句包括一些物理设计参数，那么完整的 DDL 规范必须等到物理数据库设计阶段完成之后。 | 数据库文件的存储结构和访问路径的初步确定。这对应于用数据存储定义语言定义内部模式。 |

数据库设计分为几个阶段。逻辑数据库设计和物理数据库设计是其中的两个。这种分离通常基于数据库管理系统的三级体系结构的概念，它提供了数据独立性。因此，我们可以说这种分离导致了数据独立性，因为逻辑数据库设计的输出是数据库系统的概念和外部层次的模式，它独立于作为内部模式的物理数据库设计的输出。

**53。什么是临时表？它们什么时候有用？**
临时表仅针对特定会话存在，或者其数据在事务期间持续存在。临时表通常用于支持专门的汇总或特定的应用程序处理要求。与永久表不同，创建临时表时不会为其分配空间。插入行时，将为表动态分配空间。“创建全局临时表”命令用于在 Oracle 中创建临时表。

**54。解释发生在** **甲骨文数据库中的不同类型的故障。**
**故障类型–**在 Oracle 数据库中，可能会发生以下故障类型:

*   **声明失败**
*   **不良数据类型**
    *   空间不足
*   **权限不足**(例如，角色的对象权限)
*   **用户流程失败**
    *   用户执行了异常断开
    *   用户的会话异常终止
    *   用户的程序引发了地址异常
*   **用户错误**
    *   用户放下一张桌子
    *   用户通过修改损坏数据
*   **实例故障**
*   **媒体故障**
    *   用户放下一张桌子
    *   用户通过修改损坏数据
*   **警报日志**
    *   记录信息和错误消息
    *   所有实例的启动和关闭都记录在日志中

**55。RAID 技术的主要目标是什么？**

**RAID** 代表**R**edundant**A**array of**I**NEX pensive(或有时“独立”) **D** isks。

RAID 是一种将多个硬盘驱动器组合成一个逻辑单元的方法(两个或多个磁盘组合在一起，在主机系统中显示为一个设备)。开发 RAID 技术是为了解决传统磁盘存储的容错和性能限制。与单个硬盘或一组独立硬盘相比，它可以提供容错能力和更高的吞吐量。虽然阵列曾经被认为是复杂且相对专业化的存储解决方案，但如今它们易于使用，并且对于广泛的客户端/服务器应用程序至关重要。

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>