# SQL 中的 SELECT INTO 语句

> 原文:[https://www.geeksforgeeks.org/select-into-statement-in-sql/](https://www.geeksforgeeks.org/select-into-statement-in-sql/)

**SQL 中的 SELECT INTO** 语句一般用于批量复制目的。我们可以使用一个命令将整个数据从一个表复制到另一个表中。

**注意:**
查询是在 SQL SERVER 中执行的，它们可能无法在许多在线 SQL 编辑器中工作，所以最好使用离线编辑器。

**语法:**

```
SELECT column1, column2..... INTO TARGET_TABLE from SOURCE_TABLE 
```

目标表应该具有与源表相同的模式和数据类型。

让我们首先创建一个表 GFG _ 员工:

```
create table GFG_Employees 
 (
  id int,
  name varchar(20),
  email varchar(max),
  department varchar(20)
 ) ;

insert into GFG_EMPLOyees values(1, 'Jessie', 'jessie23@gmail.com', 'Development'); 
insert into GFG_EMPLOyees values(2, 'Praveen', 'praveen_dagger@yahoo.com', 'HR');
insert into GFG_EMPLOyees values(3, 'Bisa', 'dragonBall@gmail.com', 'Sales'); 
insert into GFG_EMPLOyees values(4, 'Rithvik', 'msvv@hotmail.com', 'IT'); 
insert into GFG_EMPLOyees values(5, 'Suraj', 'srjsunny@gmail.com', 'Quality Assurance');
insert into GFG_EMPLOyees values(6, 'Om', 'OmShukla@yahoo.com', 'IT');
insert into GFG_EMPLOyees values(7, 'Naruto', 'uzumaki@konoha.com', 'Development'); 
```

<center>

| 身份 | 名字 | 电子邮件 | 部门 |
| --- | --- | --- | --- |
| one | 杰西（Janet 的苏格兰名的昵称）（f.） | jessie23@gmail.com | 发展 |
| Two | Praveen | praveen_dagger@yahoo.com | 人力资源（部） |
| three | 能 | 龙珠登场人物及译名列表 | 销售 |
| four | Rithvik | msvv@hotmail . com | 信息技术 |
| five | 苏拉杰 | 开源软件国际化之简体中文组 | 质量保证 |
| six | 功绩勋章 | o msconfig @ Yahoo . com | 信息技术 |
| seven | 鸣人 | 乌祖玛基@konoha.com | 发展 |

</center>

**查询-1:** 将 GFG_Employees 的所有数据复制到 backUpEmployee 表中。

```
SELECT * INTO backUpEmployee from GFG_Employees; 
```

**输出:**

```
Select * from backUpEmployee;
```

<center>

| 身份 | 名字 | 电子邮件 | 部门 |
| --- | --- | --- | --- |
| one | 杰西（Janet 的苏格兰名的昵称）（f.） | jessie23@gmail.com | 发展 |
| Two | Praveen | praveen_dagger@yahoo.com | 人力资源（部） |
| three | 能 | 龙珠登场人物及译名列表 | 销售 |
| four | Rithvik | msvv@hotmail . com | 信息技术 |
| five | 苏拉杰 | 开源软件国际化之简体中文组 | 质量保证 |
| six | 功绩勋章 | o msconfig @ Yahoo . com | 信息技术 |
| seven | 鸣人 | 乌祖玛基@konoha.com | 发展 |

</center>

**查询-2:** 使用“where”子句仅将 GFG_Employees 中的一些行复制到 backUp2 表中。

```
SELECT * INTO backUp2 from GFG_Employees where department in ('Development', 'IT'); 
```

**输出:**

```
Select * from backUp2; 
```

<center>

| 身份 | 名字 | 电子邮件 | 部门 |
| --- | --- | --- | --- |
| one | 杰西（Janet 的苏格兰名的昵称）（f.） | jessie23@gmail.com | 发展 |
| four | Rithvik | msvv@hotmail . com | 信息技术 |
| six | 功绩勋章 | o msconfig @ Yahoo . com | 信息技术 |
| seven | 鸣人 | 乌祖玛基@konoha.com | 发展 |

</center>

**查询-3:** 要仅将 GFG_Employees 表中的一些列复制到 backUp3 表中，请在查询中指定它们。

```
SELECT id, name INTO backUp3 from GFG_Employees; 
```

**输出:**

```
Select * from backUp3; 
```

<center>

| 身份 | 名字 |
| --- | --- |
| one | 杰西（Janet 的苏格兰名的昵称）（f.） |
| Two | Praveen |
| three | 能 |
| four | Rithvik |
| five | 苏拉杰 |
| six | 功绩勋章 |
| seven | 鸣人 |

</center>

**INSERT INTO SELECT vs SELECT INTO:**
这两个语句都可以用来将数据从一个表复制到另一个表。但是，只有当目标表存在时，才能使用 INSERT INTO SELECT，而即使目标表不存在，也可以使用 SELECT INTO 语句，因为如果目标表不存在，它会创建目标表。

```
INSERT INTO tempTable select * from GFG_Employees; 
```

这里的表 tempTable 应该存在或者预先创建，否则会抛出一个错误。
![](img/80a67d784cfa64dbc26a225465faf78f.png)

```
SELECT * INTO backUpTable from GFG_Employees;
```

这里没有必要在之前存在，因为如果表不存在，SELECT INTO 会创建一个表，然后复制数据。