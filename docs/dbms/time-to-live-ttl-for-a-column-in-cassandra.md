# 卡珊德拉某栏目生存时间(TTL)

> 原文:[https://www . geesforgeks . org/生存时间-TTL-for-a-column-in-Cassandra/](https://www.geeksforgeeks.org/time-to-live-ttl-for-a-column-in-cassandra/)

在本文中，我们将讨论如何使用**生存时间(TTL)** 命令插入和更新，以及如何确定现有列的过期时间限制。
在[中卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)生存时间(TTL)扮演着重要的角色，而如果我们想要设置一个列的时间限制，并且我们想要在一个时间点之后自动删除，那么在当时使用 TTL 关键字来定义特定列的时间限制是非常有用的。

1.  在 Cassandra 中，INSERT 和 UPDATE 命令都支持为列中的数据设置过期时间。
2.  它用于设置特定时间段的时间限制。通过使用 TTL 子句，我们可以在插入时设置 TTL 值。
3.  我们可以使用 TTL 函数来获取特定选定查询的剩余时间。
4.  在插入点，我们可以使用 TTL 子句设置插入数据的过期限制。让我们考虑一下，如果我们想将过期限制设置为两天，那么我们需要定义其 TTL 值。
5.  通过使用 TTL，我们可以将有效期设置为两天，TTL 的值将为 172800 秒。让我们用一个例子来理解。

表格:学生注册
创建表格使用了以下 CQL 查询。

```
CREATE TABLE student_Registration(
Id int PRIMARY KEY,
Name text,
Event text
);

```

**使用 TTL 插入:**
要使用 TTL 插入数据，请使用以下 CQL 查询。

```
INSERT INTO student_Registration (Id, Name, Event) 
       VALUES (101, 'Ashish', 'Ninza') USING TTL 172800;
INSERT INTO student_Registration (Id, Name, Event) 
       VALUES (102, 'Ashish', 'Code') USING TTL 172800;
INSERT INTO student_Registration (Id, Name, Event) 
       VALUES (103, 'Aksh', 'Ninza') USING TTL 172800; 
```

**输出:**

<center>

| 身份 | 名字 | 事件 |
| --- | --- | --- |
| One hundred and one | Ashish | 宁萨 |
| One hundred and two | Ashish | 密码 |
| One hundred and three | 阿克什 | 宁萨 |

</center>

现在，要确定特定列的剩余过期时间，请使用以下 CQL 查询。

```
SELECT TTL (Name) 
from student_Registration 
WHERE Id = 101; 
```

**输出:**

<center>

| 名称 |
| --- |
| One hundred and seventy-two thousand seven hundred |

</center>

它会减少，因为您将再次检查其 TTL 值，只是因为 TTL 时间限制。现在，使用下面的 CQL 查询来再次检查。

```
SELECT TTL (Name) 
from student_Registration 
WHERE Id = 101; 
```

**输出:**

<center>

| 名称 |
| --- |
| One hundred and seventy-two thousand five hundred |

</center>

**使用 TTL 更新:**
现在，如果我们想延长时间限制，那么我们可以借助 UPDATE 命令和 using TTL 关键字进行延长。让我们看看。为了将时间限制延长 3 天并将名称更新为“rana ”,使用了以下 CQL 查询。

```
UPDATE student_Registration
USING TTL 259200 
SET Name = 'Rana' 
WHERE Id= 102 
```

**输出:**

<center>

| 身份 | 名字 | 事件 |
| --- | --- | --- |
| One hundred and one | Ashish | 宁萨 |
| One hundred and two | 中国林蛙 | 密码 |
| One hundred and three | 阿克什 | 宁萨 |

</center>

```
SELECT TTL (Name) 
from student_Registration 
WHERE Id = 102; 
```

**输出:**

<center>

| 名称 |
| --- |
| Two hundred and fifty-nine thousand one hundred |

</center>

**使用 TTL 删除列:**
要删除特定的现有列，请使用以下 CQL 查询。

```
UPDATE student_Registration
USING TTL 0 
SET Name = 'Ashish' 
WHERE Id = 102; 
```

**注意:**我们可以使用 TTL 的默认值来设置整个表格的默认 TTL。

参考–[https://docs.datastax.com/](https://docs.datastax.com/en/cql/3.3/cql/cql_reference/cqlCreateTable.html#tabProp__cqlTableDefaultTTL)