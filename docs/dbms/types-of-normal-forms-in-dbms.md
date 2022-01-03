# 数据库管理系统中范式的类型

> 原文:[https://www . geeksforgeeks . org/DBMS 中的范式类型/](https://www.geeksforgeeks.org/types-of-normal-forms-in-dbms/)

[数据库规范化](https://www.geeksforgeeks.org/introduction-of-database-normalization/)只不过是通过应用一些通用规则来构建关系数据库管理系统的过程，这些规则要么是通过创建新的数据库设计，要么是通过用一系列所谓的范式进行分解，这些范式是:

1.  非标准化形式或联合国基金会
2.  第一范式或 1NF
3.  第二范式或 2NF
4.  第三范式或 3NF
5.  主键范式
6.  抵制 Codd 范式或 BCNF
7.  第四范式或 4NF
8.  本质元组范式
9.  第五范式或 5NF
10.  域密钥范式
11.  第六范式或 6NF

**1。非正规形式或 UNF:**
它是最简单的数据库模型，也称为非第一正规形式(NF2)。联合国基金会的模型会遇到数据冗余等问题，因此缺乏数据库规范化的效率。

**例:**
学生表:

```
StudentId      Name       Course 

  101           Raj        Mathematics
                          Chemistry
  102          Nilesh      Chemistry
  103          Sanu        Physics
                          Chemistry
```

在上面的示例中，数据是未规范化的形式，因为该表在课程元组中包含多值属性。但是非规范化表单也有几个优点(这就是为什么我们仍然使用它，尽管它缺少数据库规范化的几个优点)，它们是:

1.  联合国基金会可以处理复杂的数据结构，
2.  在联合国基金会查询更简单，
3.  重组数据更容易。

使用这个更容易查询的功能 [NoSQL 数据库](https://www.geeksforgeeks.org/introduction-to-nosql/)像[蒙古数据库](https://www.geeksforgeeks.org/mongodb-an-introduction/)、[阿帕奇](https://www.geeksforgeeks.org/apache-poi-introduction/)等。因此像谷歌、亚马逊和脸书这样的科技巨头用它来处理大量难以存储的日常数据。

**2。[第一范式或 1NF](https://www.geeksforgeeks.org/first-normal-form-1nf/) :**
只有当关系表不包含任何多值属性但只包含单值属性时，关系才处于第一范式。

**例:**
学生表:

```
StudentId      Name       Course1        course2 

  101          Raj         Mathematics    Chemistry
  102          Nilesh      Chemistry
  103          Sanu        Physics        Chemistry

```

为了确保这个模型是第一范式，我们将课程元组(前面的例子)分成课程 1 和课程 2，以原子实体的形式保存我们的课程信息，这样没有一行包含多个课程。

**3。[第二范式或 2NF](https://www.geeksforgeeks.org/second-normal-form-2nf/) :**
关系处于第二范式，如果:

*   它处于第一范式或 1NF
*   它不包含任何部分依赖关系。(它不应该有任何功能上依赖于关系的候选键的任何适当子集的非质数属性。).

**4。[第三范式或 3NF](https://www.geeksforgeeks.org/third-normal-form-3nf/) :**
假设 R 是关系模式，X- > Y 对 R 的任何非平凡函数依赖都在 3NF 中，如果:

*   r 应该在 2NF
*   x 应该是候选键或超键，或者
*   y 应该是主要属性

(所以基本上关系已经在 2NF 中了，如果它不包含任何传递依赖，那么它将在 3NF 中。).

**5。初等键范式或 EKNF:**
它是第三范式的改进版本，因此一般来说 EKNF 本身就是第三范式。当有多个唯一的复合键并且这些键重叠时，这导致重叠列中的冗余。

因此，如果在 3NF 关系中，每一个非平凡的函数依赖都涉及一个超级键或一个基本键的子键，那么它就在 EKNF 中。

**6。[抵制 Codd 范式或 BCNF](https://www.geeksforgeeks.org/boyce-codd-normal-form-bcnf/) :**
让 R 成为关系模式

*   ![X->Y](img/e74acd7ea56137b33f12fa347fc4e34c.png "Rendered by QuickLaTeX.com")be any non-trivial functional dependency over the R is BCNF if X is a Candidate Key or a SuperKey.

    或者

*   ![X->Y](img/e74acd7ea56137b33f12fa347fc4e34c.png "Rendered by QuickLaTeX.com")是微不足道的函数依赖(即 X 的 Y 子集)，

因此，BCNF 没有任何功能依赖的冗余，是 3NF 的稍强版本。

**7。第四范式还是 4NF:**
4NF 不过是 BCNF 的下一级。2NF、3NF 和 BCNF 关注的是函数依赖，而 4NF 关注的是多值依赖。

假设 R 是关系模式，F 是单值和多值依赖关系![X->->Y](img/58e2ba4ae914165fa03cc276e1be17c7.png "Rendered by QuickLaTeX.com")在 4NF，如果:

*   X is a candidate key or a super key of the relation,

    或者

*   x 联合 Y = R

**8。ETNF:**
ETNF 是本质元组范式，比第四范式严格，但没有第五范式严格。需要 ETNF 来消除元组中的冗余。一个关系将在 ETNF 中，该关系在 BCNF(仅由函数和连接依赖项指定)，并且一些键只有一个属性。(如果每个键只有一个属性，那么 5NF 中的关系。).这是 ETNF 中一个关系的简单充分条件。

在 ETNF 中，每个显式连接依赖项的组件都是一个超键。

**9。第五范式或 5NF:**
5NF 也称为项目-加入范式或 PJ/NF。5NF 旨在减少关系数据库中的冗余。为了避免冗余，所有的表都被分成尽可能多的 5NF 表。当每一个非平凡的连接依赖都被该关系的候选键所暗示时，表就是 5NF 的。(不应该包含任何连接依赖项，并且连接应该是无损的。).

**10。域密钥范式或 DKNF:**
这是一种范式，其中数据库只包含两个约束，它们是:

1.  领域限制，
2.  关键制约因素。

域约束的功能是指定给定属性的允许值，而键约束的主要功能是指定唯一标识给定表中某一行的属性。
领域关键范式避免所有非时间异常。

请始终记住，无法用外键表达的关系显然违反了域键范式。

**11 时。第六范式或 6NF:**
只有当一个关系不支持任何非平凡的连接依赖时，它才处于 6NF。任何在 6NF 的关系也应该在 5NF。虽然一些作者使用术语第六范式作为 DKNF 的同义词，但是 6NF 比域键范式更严格，冗余更少。

6NF 将关系变量分解成不可约成分。这对于非时间关系变量来说相对不重要，但是当我们处理时间变量或其他区间数据时很重要。第六种范式用于许多利大于弊的数据仓库。

规范化必然涉及到组织数据库的列或属性以及表，以确保它们的依赖关系被数据库完整性约束正确地实施