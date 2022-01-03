# MySQL 中的克隆表

> 原文:[https://www.geeksforgeeks.org/cloning-table-in-mysql/](https://www.geeksforgeeks.org/cloning-table-in-mysql/)

在许多情况下，您可能需要创建一个已经定义(或创建)的表的精确副本。 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql) 可以让你执行这个操作。因为我们可能需要这样的重复表来测试数据，而不会对原始表和存储在其中的数据产生任何影响。

**原始 _ 表格–**

<center>

| 身份证明 | F_name | L_name | 项目 id | 电子邮件 | 职务 _ 头衔 | 城市 | 年龄 | 薪水 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1. | 马达夫 | 莫汉·夏尔马 | A-1 | W_@。com | SDE | 阿格拉 | Twenty-one | 70,000/- |
| 2. | 穆古 | 莫汉·夏尔马 | B-2 | V_@。com | SDE | 德里 | Twenty-one | 70,000/- |
| 3. | 喋喋不休的人 | 夏尔马 | C-3 | X_@。com | SDE 先生 | [军]爆破筒 | Twenty-nine | 1,50,000/- |
| 4. | 保劳格 | 夏尔马 | D-4 | y_@。com | SDE | 孟买 | Twenty-seven | 80,000/- |
| 5. | 安西卡 | 戈亚尔 | E-5 | Z_@。com | Hr Mgr(人力资源管理系统管理员) | 无聊死了 | Twenty-six | 90,000/- |

</center>

复制(克隆)现有表模式(结构)及其内容的步骤–

**步骤 1 :** 要克隆表，请使用下面的查询。使用此查询，可以创建一个空的表模式(结构)，其属性与原始表相同:

```
CREATE TABLE Contact List(Clone_1) LIKE Original_table;
```

**输出:联系人列表(Clone_1)**

<center>

| 身份证明 | F_name | L_name | project_id | 电子邮件 | 职务 _ 头衔 | 城市 | 年龄 | 薪水 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

</center>

**第二步:**如果你想创建一个表，这个表被你的原始表的所有内容装饰起来，使用这个 MySQL 查询:

```
CREATE TABLE Contact List(Clone_1) AS SELECT * 
FROM Original_table; 
                 OR
INSERT INTO Contact List(Clone_1) SELECT * 
FROM original_table;
```

**输出:联系人列表(Clone_1)**

<center>

| 身份证明 | F_name | L_name | 项目 id | 电子邮件 | 职务 _ 头衔 | 城市 | 年龄 | 薪水 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1. | 马达夫 | 莫汉·夏尔马 | A-1 | W_@。com | SDE | 阿格拉 | Twenty-one | 70,000/- |
| 2. | 穆古 | 莫汉·夏尔马 | B-2 | V_@。com | SDE | 德里 | Twenty-one | 70,000/- |
| 3. | 喋喋不休的人 | 夏尔马 | C-3 | X_@。com | SDE 先生 | [军]爆破筒 | Twenty-nine | 1,50,000/- |
| 4. | 保劳格 | 夏尔马 | D-4 | y_@。com | SDE | 孟买 | Twenty-seven | 80,000/- |
| 5. | 安西卡 | 戈亚尔 | E-5 | Z_@。com | Hr Mgr(人力资源管理系统管理员) | 无聊死了 | Twenty-six | 90,000/- |

</center>