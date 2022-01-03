# TCL 完整形式

> 原文:[https://www.geeksforgeeks.org/tcl-full-form/](https://www.geeksforgeeks.org/tcl-full-form/)

**TCL** 代表**交易控制语言**。这些命令用于维护数据库的一致性和管理由 DML 命令进行的事务。

一个**事务**是一组 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 语句，对存储在数据库管理系统中的数据执行。无论何时进行任何事务，这些事务都暂时发生在数据库中。因此，为了使更改永久化，我们使用 **TCL** 命令。

TCL 命令包括:

1.  犯罪
2.  反转
3.  保存点

**1。COMMIT :**
此命令用于永久保存数据。
每当我们执行任何 DDL 命令，如插入、删除或更新，如果数据没有永久存储，这些都可以回滚。所以为了安全起见，使用了 COMMIT 命令。

**语法:**

```
commit; 
```

**2。回滚:**
此命令用于获取数据或将数据恢复到最后一个保存点或最后一次提交的状态。如果由于某些原因，插入、删除或更新的数据不正确，您可以将数据回滚到特定的保存点，或者如果保存点没有完成，则回滚到上次提交的状态。

**语法:**

```
rollback;
```

**3。保存点:**
该命令用于临时保存特定点的数据，以便在需要时可以回滚到该特定点。

**语法**:

```
Savepoint A; 
```

考虑以下表格学生:

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 非常 | Sixty-five |
| 舒赞 | Seventy |

```
UPDATE STUDENT 
SET NAME = ‘Sherlock’ 
WHERE NAME = ‘Jolly’;

COMMIT;
ROLLBACK; 
```

使用此命令，您可以使用 **COMMIT** 命令更新记录并永久保存。

现在在 COMMIT 之后:

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 谢洛克 | Sixty-five |
| 舒赞 | Seventy |

</figure>

如果未执行提交，则更新命令所做的更改可以回滚。

现在如果没有执行**提交**。

```
UPDATE STUDENT 
SET NAME = ‘Sherlock’ 
WHERE STUDENT_NAME = ‘Jolly’; 
```

更新命令后，表格将为:

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 谢洛克 | Sixty-five |
| 舒赞 | Seventy |

现在如果在上表中执行**回滚**:

```
rollback; 
```

回滚后:

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 非常 | Sixty-five |
| 舒赞 | Seventy |

如果在上表中执行了保存点:

```
INSERT into STUDENT 
VALUES ('Jack', 95);

Commit;

UPDATE NAME 
SET NAME= ‘Rossie’ 
WHERE marks= 70;

SAVEPOINT A;

INSERT INTO STUDENT 
VALUES (‘Zack’, 76);

Savepoint B;

INSERT INTO STUDENT 
VALUES (‘Bruno’, 85);

Savepoint C;

SELECT * 
FROM STUDENT; 
```

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 非常 | Sixty-five |
| 萝茜 | Seventy |
| 插口 | Ninety-five |
| 六便士之硬币 | Seventy-six |
| 布鲁诺 | eighty-five |

</figure>

现在，如果我们回滚到保存点 B:

```
Rollback to B; 
```

生成的表格将是-

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 非常 | Sixty-five |
| 萝茜 | Seventy |
| 插口 | Ninety-five |
| 六便士之硬币 | Seventy-six |

现在，如果我们回滚到保存点 A:

```
Rollback to A; 
```

生成的表格将是-

<figure class="table">

| 名字 | 马克斯（英格兰人姓氏） |
| --- | --- |
| 约翰 | Seventy-nine |
| 非常 | Sixty-five |
| 萝茜 | Seventy |
| 插口 | Ninety-five |

所以这都是关于 SQL(事务控制语言)中的 **TCL** 命令的例子。

</figure>

</figure>

</figure>

</figure>

</figure>