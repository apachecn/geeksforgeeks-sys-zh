# 使用卡珊德拉中的表定义创建实体化视图

> 原文:[https://www . geesforgeks . org/creating-物化视图-使用-表-定义-in-cassandra/](https://www.geeksforgeeks.org/creating-materialized-view-using-table-definition-in-cassandra/)

在本文中，我们将讨论如何基于一个特定的问题创建一个物化视图，并介绍同样的例子。我们一个一个来讨论。

**先决条件**–[实体化视图](https://www.geeksforgeeks.org/materialized-views-in-cassandra/)

在本文中，您将看到如何基于表定义创建实体化视图。让我们通过下面给出的步骤来理解这一点。

**创建表格定义:**

现在，为了理解这些场景，考虑一个例子，其中板球 _team 是一个表名，team_match_wins、team _ match _ losses 和 team_match_ties 是字段。

```
CREATE TABLE cricket_team
(
team_name text primary key,
team_match_wins int,
team_match_losses int,
team_match_ties int
);
```

**将数据插入表中:**

现在，您将看到 CQL 查询为上面创建的表插入了一些行。

```
Insert into cricket_team( team_name, team_match_wins, team_match_losses, team_match_ties) 
values ('IN' , 100, 5, 5); 
Insert into cricket_team( team_name, team_match_wins, team_match_losses, team_match_ties) 
values ('NZ' , 80, 5, 2); 
Insert into cricket_team( team_name, team_match_wins, team_match_losses, team_match_ties) 
values ('AUS' , 80, 4, 5); 
Insert into cricket_team( team_name, team_match_wins, team_match_losses, team_match_ties) 
values ('PAK' , 70, 8, 5); 
Insert into cricket_team( team_name, team_match_wins, team_match_losses, team_match_ties) 
values ('ENG' , 60, 9, 5);
```

**验证数据:**

现在，为了验证上面插入的数据，您可以使用下面的 CQL 查询。

```
 select * from cricket_team;
```

**输出:**

<figure class="table">

| 团队名称 | 团队 _ 比赛 _ 失败 | 团队 _ 比赛 _ 联系 | 团队 _ 匹配 _ 获胜 |
| --- | --- | --- | --- |
| 巴基斯坦 | eight | five | Seventy |
| 在…里 | five | five | One hundred |
| 澳大利亚 | four | five | Eighty |
| 新西兰 | five | Two | Eighty |
| 电子新闻采集 | nine | five | Sixty |

**示例–**

现在，如果你想查询如下。

```
select * cricket_team_by_team_match_wins where team_match_wins = 100;
```

**注–**

主键字段不能为空。WHERE 子句必须包含空检查。由于 SELECT 中的 WHERE 子句基于 team_match_wins，因此 team_match_wins 必须是分区键。

**创建实体化视图:**

现在，如果您要执行这个查询，您将会得到一个错误，因为没有名为**板球队**by _**队 _match_wins 的表。**因此，首先，您可以使用以下 CQL 查询创建一个实体化视图。

```
create materialized view if not exists
cricket_team_by_team_match_wins As
select * from cricket_team
where team_match_wins IS NOT NULL AND team_name IS NOT NULL
primary key((team_match_wins),team_name);
```

**执行查询:**

现在，如果您将执行下面给出的查询，那么它将成功执行。

```
select * cricket_team_by_team_match_wins where team_match_wins = 100;
```

**输出:**

<figure class="table">

| 团队 _ 匹配 _ 获胜 | 团队名称 | 团队 _ 比赛 _ 失败 | 团队 _ 比赛 _ 联系 |
| --- | --- | --- | --- |
| One hundred | 在…里 | five | five |

</figure>

</figure>