# 数据模型的构建模块

> 原文:[https://www . geeksforgeeks . org/数据模型构造块/](https://www.geeksforgeeks.org/building-blocks-of-a-data-model/)

数据模型是一种数据结构，包含数据的所有必要细节，如数据的名称、数据的大小、与其他数据的关系以及应用于数据的约束。它是一种交流工具。

为了以有序的方式存储数据库，数据模型是必不可少的。它将提供系统分析师、设计者和应用程序程序员之间的交互。它提高了对组织感兴趣的数据库设计的理解。

数据模型由构建块组成。它们是:

```
1. Entities
2. Attributes
3. Relationships 
4. Constraints  
```

下面简单解释一下。

1.  **Entities:**
    Entities are real time objects that exist.It can be a person, place, object, event, concept. Entities are represented by a rectangle box containing the entity name in it.

    *例*:学生，员工。

2.  **Attributes:**
    It is the set of characteristics representing an entity.It is represented by a ellipse symbol with attribute name on it.

    *例:*一个学生有姓名、卷号、年龄等属性。

3.  **Relationship:**
    It describes the association between two entities.It is represented using diamond symbol containing relationship name with it.The data model generally uses three kinds of relationships:one to many, many to many, one to one.

    *例:*两个实体学生和班级的关系有多对多的关系。

4.  **Constraints:**
    Constraints are conditions applied on the data.It provides the data integrity.

    *示例:*一个学生最多可以从图书馆拿 2 本书被应用为学生数据库上的一个约束。