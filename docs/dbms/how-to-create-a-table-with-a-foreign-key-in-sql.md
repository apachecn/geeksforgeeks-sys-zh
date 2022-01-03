# 如何在 SQL 中创建带外键的表？

> 原文:[https://www . geeksforgeeks . org/如何使用 sql 中的外键创建表/](https://www.geeksforgeeks.org/how-to-create-a-table-with-a-foreign-key-in-sql/)

[**结构化查询语言**](https://www.geeksforgeeks.org/structured-query-language/) 或 SQL 是一种标准的数据库语言，用于创建、维护和检索关系数据库中的数据，如 MySQL、Oracle、SQL Server、PostGre 等。

为了创建带有外键的表，我们必须了解几个键约束:

**超级键:**

唯一标识关系中元组的属性或属性集。

例:那么考虑一个*客户数据库*，

关系客户的 *customer_id* 足以区分一个元组和另一个元组。因此， *customer_id* 是一把超级钥匙。同样的， *customer_id* 和 *customer_name* 的组合对于关系客户来说也是超级关键。这里的*客户 _ 姓名*不是超级钥匙，因为可能几个人同名。

**候选键:**

一个超级键，使得关系中没有合适的子集是超级键。

例:*客户名称*和*客户街道*的组合足以区分客户关系的成员。那么， *{customer_id}* 和 *{customer_name，customer_street}* 都是候选键。虽然 *customer_id* 和 *customer_name* 一起可以区分客户元组，但是它们的组合并不能形成候选键，因为只有 *customer_id* 才是候选键。

**主键:**

选择候选关键字来唯一标识关系中的元组。在所有可用的候选键中，数据库设计者可以识别一个主键。未被选为主键的候选键称为备用键。

例:对于客户关系，我们可以选择 *customer_id* 作为主键。

**外键:**

外键表示表之间的关系。外键是一列(或一组列)，其值从其他表的主键派生而来。定义外键的表称为外键表或详细信息表。定义主键并被外键引用的表称为主键表或主表。

我们可以通过以下方式向关系添加外键

**方法-1 :**

**语法:**

```
CREATE TABLE TABLE_NAME(
    Column 1 datatype,
    Column 2 datatype,
    Column 3 datatype FOREIGN KEY REFERENCES Table_name(Column name), //Column which has to be a forigen key
    ..
    ..
    Column n
)
```

考虑以下客户关系

<figure class="table">

| 客户 id | 客户名称 | 客户地址 |
| --- | --- | --- |
| One hundred and one | 极客 1 | 金奈 |
| One hundred and two | 极客 2 | 德里 |
| One hundred and three | 极客 3 | MUMBAI 的原称 |
| One hundred and four | 极客 4 | 浦那 |
| One hundred and five | 极客 5 | 纳西克 |

为了创建下表，我们使用以下命令

```
CREATE TABLE Customer(
    Customer_id int primary key,
    Customer_name varchar(20),
    Customer_Address varchar(20),
)
```

现在考虑销售关系

<figure class="table">

| 客户 id | 项目标识 | 支付模式 |
| --- | --- | --- |
| One hundred and one | One million three hundred and thirty-four thousand one hundred and fifty-one | 货到付款 |
| One hundred and one | Sixteen thousand six hundred and fifty-two | 借记卡 |
| One hundred and four | One thousand and nine | 贝宝 |
| One hundred and two | Fourteen thousand five hundred and forty-three | 货到付款 |

所以在这个关系中， *Customer_id* 是从上面的客户关系中获取的外键。我们可以使用以下命令创建该表。

```
CREATE TABLE SALES(
    Customer_id int FOREIGN KEY REFERENCES Customer(Customer_id)
    Item_id int,
    Payment_Mode varchar(20), 
)
```

**方法-2 :**

**语法:**

```
CREATE TABLE TABLE_NAME(
    Column 1 datatype,
    Column 2 datatype,
    Column 3 datatype  //Column which has to be a forigen key
    ..
    ..
    Column n
    CONSTRAINT Constraint_name FOREIGN KEY (Column name) REFERENCES Table_Name(Column name),
)
```

现在，为了使用客户表创建相同的销售表，我们可以运行以下命令

```
CREATE TABLE SALES(
    Customer_id int,
    Item_id int,
    Payment_Mode varchar(20),
    CONSTRAINT FK_Sales FOREIGN KEY (Customer_id)REFERENCES Customer(Customer_id)
)
```

<figure class="table">

| 客户 id | 项目标识 | 支付模式 |
| One hundred and one | One million three hundred and thirty-four thousand one hundred and fifty-one | 货到付款 |
| One hundred and one | Sixteen thousand six hundred and fifty-two | 借记卡 |
| One hundred and four | One thousand and nine | 贝宝 |
| One hundred and two | Fourteen thousand five hundred and forty-three | 货到付款 |

</figure>

然后我们得到以 customer_id 为外键的下表。

</figure>

</figure>