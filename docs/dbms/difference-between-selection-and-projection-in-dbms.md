# 数据库管理系统中选择和投影的区别

> 原文:[https://www . geesforgeks . org/DBMS 中选择和投影的区别/](https://www.geeksforgeeks.org/difference-between-selection-and-projection-in-dbms/)

先决条件–[关系代数](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)
**1。[选择](https://www.geeksforgeeks.org/select-operation-in-relational-algebra/) :**
该操作从满足选择语法中提到的给定条件的关系中选择元组子集。

符号–

```
σc (R)
```

这里，‘c’是选择条件，‘σ(sigma)’用来表示**选择操作符**。

**2。[投射](https://www.geeksforgeeks.org/project-operation-in-relational-algebra/) :**
该操作选择某些需要的属性，同时丢弃其他属性。

符号–

```
πA (R)
```

其中‘A’是属性列表，它是来自关系(R)的属性的期望属性集，
符号‘π(pi)’用来表示 Project 运算符，
R 一般是关系代数表达式，它产生一个关系。

**数据库管理系统中选择和投影的区别**

| 南号码 | 种类 | 选择 | 推断 |
| --- | --- | --- | --- |
| 1. | 其他名称 | 选择操作也称为水平分区。 | 项目操作也称为垂直分区。 |
| 2. | 使用 | 它用于从满足选择语法中提到的给定条件的关系中选择元组子集。 | 它用于选择某些必需的属性，同时丢弃其他属性。 |
| 3. | 分割 | 它水平分割表格。 | 它垂直分隔桌子。 |
| 4. | 哪个先用的 | 选择操作在投影之前执行(如果它们要一起使用)。 | 投影操作在选择后执行(如果它们要一起使用)。 |
| 5. | 使用的运算符 | 选择运算符用于选择操作。 | 投影操作中使用了投影运算符。 |
| 6. | 操作员符号 | 选择运算符由适马符号表示。 | 项目操作符用圆周率符号表示。 |
| 7. | 交换的 | 选择是可交换的。 | 投影是不可交换的。 |
| 8. | 列选择 | Select 用于选择特定元组的所有列。 | 项目用于选择特定的列。 |
| 9. | 使用的 SQL 语句 | 选择，从，在 | 选择，从 |