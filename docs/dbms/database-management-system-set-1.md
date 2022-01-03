# 数据库管理系统|第 1 套

> 原文:[https://www . geesforgeks . org/database-management-system-set-1/](https://www.geeksforgeeks.org/database-management-system-set-1/)

GATE CS 考试中提出了以下问题。

**1。给定关系**

***员工(姓名、工资、部门)*和
部门(部门、部门、地址)**

 **以下哪个查询不能用基本关系代数
运算(U，-，x，π，σ，p)来表示？(GATE CS 2000)** 
(a)每位员工的部门地址
(b)姓名与其部门名称相同的员工
(c)所有员工的工资总和
(d)给定部门的所有员工

**回答:** (c)

**说明:**
关系代数的六个基本算子是选择(σ)、投影(π)、笛卡儿积(x)(也称为叉积或交叉连接)、集并(U)、集差(-)、重命名(p)。这六个运算符是基本的，因为它们都不能省略而不失去表达能力。根据这六个定义了许多其他操作符。其中最重要的是集合交集、除法和自然连接，但是使用这些基本的关系代数操作是不可能聚合的。因此，我们不能用六个操作计算所有员工的工资总和。

**参考文献:**
[http://en.wikipedia.org/wiki/Relational_algebra](http://en.wikipedia.org/wiki/Relational_algebra)
[http://facility . ksu . edu . sa/Zito uni/203% 20 haseb % 20% 20 recture % 20 notes/Relional % 20 代数. pdf](http://faculty.ksu.edu.sa/zitouni/203%20Haseb%20%20Lecture%20Notes/Relional%20Algebra.pdf) 

 **2。给定以下关系实例。**

```
x  y  z
1  4  2
1  5  3
1  6  3
3  2  2 
```

**实例满足以下哪些功能依赖？(GATE CS 2000)**
(a) XY - > Z 和 Z - > Y
(b) YZ - > X 和 Y - > Z
(c) YZ - > X 和 X - > Z
(d) XZ - > Y 和 Y - > X

**回答:** (b)

**解释:**
函数依赖(FD)是数据库关系中两组属性之间的约束。一个 FD X- > Y 要求 X 的值唯一决定 Y 的值，其中 X 和 Y 是一组属性。FD 是钥匙概念的概括。

假设 X、Y 和 Z 是关系 R 中的属性集，可以推导出函数依赖的几个性质。其中最重要的是阿姆斯特朗的公理，用于数据库规范化:

```

* Subset Property (Axiom of Reflexivity): If Y is a subset of X, then X ? Y
* Augmentation (Axiom of Augmentation): If X -> Y, then XZ -> YZ
* Transitivity (Axiom of Transitivity): If X -> Y and Y -> Z, then X -> Z
```

从这些规则中，我们可以推导出这些次要规则:

```

* Union: If X -> Y and X -> Z, then X -> YZ
* Decomposition: If X -> YZ, then X -> Y and X -> Z
* Pseudotransitivity: If X -> Y and YZ -> W, then XZ -> W
```

在上面的问题中，Y 唯一地确定了 X 和 Z，对于给定的 Y 值，您可以很容易地找到 X 和 Z 的值。
所以，Y - > X 和 Y - > Z 适用于上面的模式。
从增广规则我们可以说 YZ- > X .如果我们理解 FD 的概念，我们不需要应用公理来找出哪个选项是真的，仅仅通过查看模式和选项我们就可以说(b)是真的。

**参考文献:**
[http://www . CSE . iitb . AC . in/~ sudarsha/db-book/slide-dir/ch7 . pdf](http://www.cse.iitb.ac.in/~sudarsha/db-book/slide-dir/ch7.pdf)
[http://en.wikipedia.org/wiki/Functional_dependency](http://en.wikipedia.org/wiki/Functional_dependency)

 **3。给定关系 r(w，x)和 s(y，z)，
从 r，s
中选择不同的 w，x
的结果保证与 r 相同，前提是(GATE CS 2000)**
(a) r 无重复且 s 非空
(b) r 和 s 无重复
(c) s 无重复且 r 非空
(d) r 和 s 具有相同数量的元组

**回答:**(一)

**说明:**
查询选择 r 的所有属性，由于我们在查询中有 distinct，所以只有 r 没有重复，结果才能等于 r。

如果我们没有给出任何想要连接两个表的属性，那么上面的查询就相当于[笛卡尔乘积](http://en.wikipedia.org/wiki/Cartesian_product)。如果两套中的任何一套是空的，卡地亚产品将是空的。因此，s 应该至少有一条记录来获取 r 的所有行。

 **4。在 SQL 中，关系可以包含空值，与空值的比较被视为未知。假设所有带有空值的比较都被视为假。
下列哪对不等价？(GATE CS 2000)**
(a) x = 5，not (not (x = 5)
(b) x = 5，x > 4 和 x < 6，其中 x 是整数
(c) x < 5，not(x = 5)
(d)以上都不是

**回答** (c)

**解释:**
不需要太多解释。对于所有小于 5 的值，x < 5 将始终为真，但 x = 5 将为假。

 **5。考虑一个模式 R(A，B，C，D)和函数依赖项 A - > B 和 C - > D，然后将 R 分解为 R1 (A，B)和 R2(C，D)是(GATE CS 2001)**
a)依赖项保持和损失较小的连接
b)损失较小的连接但不保持依赖项
c)依赖项保持但不损失较小的连接
d)不保持依赖项且不损失较小的连接

**回答:** (c)

**解释:**
**依赖保持分解:**
如果分解后功能依赖的闭包与分解前 FDs 的闭包相同，则 R 分解成 R1 和 R2 就是依赖保持分解。
一个简单的方法就是只检查我们能否从分解后存在的 FDs 中推导出所有的原始 FDs。

在上面的问题中，R(A，B，C，D)被分解成 R1 (A，B)和 R2(C，D)，并且只有两个 FDs A -> B 和 C -> D。因此，分解是依赖保持的

**无损连接分解:**
如果以下函数依赖项中至少有一个在 F+(函数依赖项的闭包)中，则将 R 分解成 R1 和 R2 是无损连接分解

```
    R1 ∩ R2 → R1
   OR
    R1 ∩ R2 → R2

```

上题中 R(A，B，C，D)分解为 R1 (A，B)和 R2(C，D)，R1∪R2 为空。所以，分解不是无损的。

**参考文献:**
[http://www . cs . sfu . ca/CC/354/Han/material/notes/354 notes-chapter 6/node 1 . html](http://www.cs.sfu.ca/CC/354/han/material/notes/354notes-chapter6/node1.html)