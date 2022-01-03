# 数据库规范化介绍

> 原文:[https://www . geesforgeks . org/数据库介绍-规范化/](https://www.geeksforgeeks.org/introduction-of-database-normalization/)

数据库规范化是组织数据库属性减少或消除**数据冗余(数据相同但位置不同)**的过程。

**数据冗余带来的问题**
数据冗余会不必要地增加数据库的大小，因为相同的数据会在许多地方重复出现。在插入、删除和更新操作中也会出现不一致的问题。

**功能依赖**
功能依赖是与数据库相关的两组属性之间的约束。功能依赖由箭头(→)表示。如果一个属性 A 在功能上决定了 B，那么就写成 A → B。

例如，employee_id → name 表示 employee_id 在功能上决定了员工的姓名。作为时间表数据库中的另一个例子，{student_id，time }→{讲课 _room}、学号和时间决定了学生应该在哪个讲课室。

**功能依赖是什么意思？**
一个函数依赖 A → B 意味着对于某个特定值 A 的所有实例，都有相同的值 B

例如，在下表中，A → B 为真，但 B → A 不为真，因为 B = 3 有不同的 A 值。

```
A   B
------
1   3
2   3
4   0
1   3
4   0
```

**平凡函数依赖**
X → Y 只有当 Y 是 X 的子集时才是平凡的
示例

```
ABC → AB
ABC → A
ABC → ABC
```

**非平凡函数依赖**
当 Y 不是 X 的子集时，X → Y 是非平凡函数依赖

当 X 相交 Y 为空时，X → Y 称为完全非平凡。

**示例:**

```
Id → Name, 
Name → DOB
```

**半非平凡函数依赖关系**
当 X 相交 Y 不为空时，X → Y 称为半非平凡。
示例:

```
AB → BC, 
AD → DC
```

*   [正常形式](https://www.geeksforgeeks.org/normal-forms-in-dbms/)
*   [标准化测验](https://www.geeksforgeeks.org/dbms-gq/database-design-normal-forms-gq/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。