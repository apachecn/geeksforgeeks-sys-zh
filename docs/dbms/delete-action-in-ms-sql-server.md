# 删除 MS SQL Server 中的动作

> 原文:[https://www . geesforgeks . org/delete-action-in-ms-SQL-server/](https://www.geeksforgeeks.org/delete-action-in-ms-sql-server/)

**先决条件–**[微软 SQL Server 中的外键](https://www.geeksforgeeks.org/foreign-key-in-ms-sql-server/)

只有当列在外键的情况下是父表的一部分时，它才能插入到子表中。外键允许我们执行称为**参考动作**的其他动作。引用操作允许在父表的情况下更新或删除行。如果用户更新/删除了父表中的一列，该列也会在子表中自动更新/删除。

**语法:**

```
foreign key(foreign-key_constraint) 
references parent_table(parentkey_column) 
ON Delete Action
```

考虑两个表——来自大学数据库的学生(父表)和分数(子表)。如果用户想要删除一列，则必须按如下所示进行:

<center>
**Table –** Student

| 名字 | 辊号 | 课程 |
| --- | --- | --- |
| 玛雅人 | One hundred and eleven | 中学生毕业考试 |
| 里亚 | One hundred and twelve | 技工 |

</center>

<center>
**Table –** Marks

| 名字 | 辊号 | 马克斯（英格兰人姓氏） |
| --- | --- | --- |
| 玛雅人 | One hundred and eleven | Seven point eight |
| 里亚 | One hundred and twelve | Seven point six |

</center>

**对表执行删除操作的 SQL 查询是–**

```
foreign key references Student(Name) 
ON Delete Action
```

**输出–**

<center>
**Table –** Student

| 名字 | 辊号 | 课程 |
| --- | --- | --- |
| – | One hundred and eleven | 中学生毕业考试 |
| – | One hundred and twelve | 技工 |

</center>

<center>
**Table –** Marks

| 名字 | 辊号 | 马克斯（英格兰人姓氏） |
| --- | --- | --- |
| – | One hundred and eleven | Seven point eight |
| – | One hundred and twelve | Seven point six |

</center>

这也会删除整个父表和子表中的行。还有其他允许的操作–无操作、级联、设置 null、设置默认值。

*   **删除时无操作–**
    它会引发一个错误，并回滚父表的删除操作。
*   **在删除级联时–**
    级联操作会删除父表和子表中的所有行。
*   **删除时设置为空–**
    只有当外键可为空时，父表和子表中的行才设置为空。
*   **删除时设置默认值–**
    只有当外键有默认定义时，如果相应的父表行被删除，则子表行被设置为默认值。