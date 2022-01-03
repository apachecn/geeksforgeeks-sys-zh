# 什么是 NULL？举个例子来说明在 SQL 中对空值的测试。什么是悬空元组问题？

> 原文:[https://www . geesforgeks . org/什么是 null-举个例子来说明-测试-sql 中的 null-什么是悬空元组-问题/](https://www.geeksforgeeks.org/what-is-null-give-an-example-to-illustrate-testing-for-null-in-sql-what-is-dangling-tuple-problem/)

**什么是 NULL？**
在结构化查询语言中，NULL 或 Null 是一种特殊类型的标记，用于告诉我们数据库中不存在数据值。在结构化查询语言中，空值是一个预定义的词，用于标识该标记。理解空值与零值完全不同是非常重要的。

换句话说，我们可以说空属性值等于无，这意味着在数据库中有一个属性的值表示无或空，一个属性不存在，或者我们可以说它丢失了。在数据库中，表中的空值是字段中显示为空的值。这是一个没有价值的领域。

**举例说明在 SQL 中测试空值的例子:**
假设有一个名为 CUSTOMERS 的表，该表具有下面给出的记录。

<figure class="table">

| 

#### Identification

 | 

#### Name

 | 

#### Age

 | 

#### Address

 | 

#### Salary

 |
| one | RAJESH | Forty-five | 印多尔 | Forty-eight thousand |
| Two | 阿努格 | Forty | UJJAIN | Fifty-seven thousand |
| three | mayank 帮的人 | Thirty-eight | 博帕尔 | Forty-five thousand |
| four | 戈拉瓦夫 | Twenty-three | 普纳 | Thirty-five thousand |
| five | 迪帕克 | Twenty-nine | 孟买 | Twenty-eight thousand |
| six | NAMAN | Twenty-five | 无聊死了 |   |
| seven | 阿尤什 | Thirty-three | 瓜廖尔 |   |

现在我们可以使用 IS NOT NULL 操作符并编写如下查询。

```
SQL> SELECT * 
FROM CUSTOMERS 
WHERE SALARY IS NOT NULL;
```

执行该查询后，将产生以下结果-

<figure class="table">

| 

#### Identification

 | 

#### Name

 | 

#### Age

 | 

#### Address

 | 

#### Salary

 |
| one | RAJESH | Forty-five | 印多尔 | Forty-eight thousand |
| Two | 阿努格 | Forty | UJJAIN | Fifty-seven thousand |
| three | mayank 帮的人 | Thirty-eight | 博帕尔 | Forty-five thousand |
| four | 戈拉瓦夫 | Twenty-three | 普纳 | Thirty-five thousand |
| five | 迪帕克 | Twenty-nine | 孟买 | Twenty-eight thousand |

这里我们可以看到，在 CUSTOMERS 表中，编号为 6 和 7 的 ID 被命名为 NAMAN 和 AYUSH，它们的工资列为空，换句话说，它为 Null。这就是为什么在查询执行之后，它会产生一个表，其中这两个名字 NAMAN 和 AYUSH 不存在，因为我们使用 IS NOT NULL 运算符。

现在我们可以使用 IS NULL 运算符并编写一个查询。

```
SQL> SELECT * 
FROM CUSTOMERS 
WHERE SALARY IS NULL;
```

执行该查询后，将产生以下结果-

<figure class="table">

| 

#### Identification

 | 

#### Name

 | 

#### Age

 | 

#### Address

 | 

#### Salary

 |
| six | NAMAN | Twenty-five | 无聊死了 |   |
| seven | 阿尤什 | Thirty-three | 瓜廖尔 |   |

这里我们可以看到，在 CUSTOMERS 表中，ID 号为 6 和 7 的名称为 NAMAN 和 AYUSH，它们的工资列为空，换句话说，它为 Null。这就是为什么在查询执行后，它会产生一个表，其中这两个名字 NAMAN 和 AYUSH 不存在，因为我们使用的是空操作符。

**什么是悬空元组问题？**
在 DBMS 中，如果有一个元组不参与自然连接，我们称之为悬空元组。这可能表明数据库中存在一致性问题。

悬空问题元组的另一个定义是，具有未出现在引用关系中的外键值的元组称为悬空元组。在数据库管理系统中，当悬空元组表示有问题时，引用完整性约束会准确地指定我们。

</figure>

</figure>

</figure>