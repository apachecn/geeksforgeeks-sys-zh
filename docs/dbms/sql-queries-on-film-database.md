# 电影数据库的 SQL 查询

> 原文:[https://www.geeksforgeeks.org/sql-queries-on-film-database/](https://www.geeksforgeeks.org/sql-queries-on-film-database/)

请考虑电影数据库中的以下表格:

```
ARTIST (Art_id, Art_Name, Art_Gender) 
PRODUCER (Prod_id, Prod_Name, Prod_Phone)
FILMS (Film_id, Film_Title, Film_Year, Film_Lang, Prod_id) 
CASTING (Art_id, Film_id, Part) 
REVIEW (Film_id, Stars) 
```

这五个表的数据内容如下所示:

```
SELECT * FROM ARTIST;
```

<center>

| Art_id | 艺术名称 | 艺术 _ 性别 |
| --- | --- | --- |
| One hundred and one | AMIT | M |
| One hundred and two | 普里塔姆 | M |
| One hundred and three | 西娅 | F |
| One hundred and four | -好的 | F |

</center>

```
SELECT * FROM PRODUCER;
```

<center>

| 产品 id | 产品名称 | 产品 _ 电话 |
| --- | --- | --- |
| Two hundred | 阿迪亚 | Six billion seven hundred and thirty-five million eight hundred and thirty-five thousand eight hundred and sixty-three |
| Two hundred and one | FARAN | Eight billion six hundred and fifty-four million two hundred and ninety-seven thousand four hundred and thirty-three |
| Two hundred and two | 亚什 | Eight billion seven hundred and sixty-five million four hundred and twenty-one thousand five hundred and sixty-seven |
| Two hundred and three | 尼拉吉 | Seven billion six hundred and fifty-four million three hundred and twenty-one thousand nine hundred and eighty-six |

</center>

```
SELECT * FROM FILMS;
```

<center>

| 电影 id | 电影 _ 标题 | 电影年 | 电影 _ 郎 | 产品 id |
| --- | --- | --- | --- | --- |
| Eleven | 战争 2 | Two thousand and seventeen | 英语 | Two hundred and one |
| Twelve | 片刻 | Two thousand and fifteen | 北印度语 | Two hundred and three |
| Thirteen | 五月 | Two thousand and nineteen | 英语 | Two hundred and one |
| Fourteen | BHANUMATI | Two thousand and fourteen | 特拉古语 | Two hundred |

</center>

```
SELECT * FROM CASTING;
```

<center>

| Art_id | 电影 id | 部分 |
| --- | --- | --- |
| One hundred and one | Twelve | 行动者 |
| One hundred and one | Eleven | 行动者 |
| One hundred and three | Thirteen | 女演员 |
| One hundred and three | Twelve | 客人 |
| One hundred and four | Fourteen | 女演员 |

</center>

```
SELECT * FROM REVIEW;
```

<center>

| 电影 id | 明星 |
| --- | --- |
| Eleven | four |
| Twelve | Two |
| Thirteen | five |
| Fourteen | four |

</center>

**查询-1:**
找到所有制片人为“NIRAJ”的电影名称。

首先，我们将找到名为“NIRAJ”的生产者的生产者标识，为此我们使用生产者表。

```
SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’
```

上面的查询将返回 Prod _ id“203”。现在我们将找到 pros_id 为“203”的电影的标题。为此，我们使用表 FILMS，并将上面的查询用作子查询。

```
SELECT FILM_TITLE 
FROM FILMS 
WHERE PROD_ID IN (SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’);
```

**输出:**

<center>

| 电影 _ 标题 |
| --- |
| 片刻 |

</center>

**Query-2:**
展示 2016 年至 2018 年间出演某部电影的所有艺人。

为了找到这一点，我们需要使用艺术家表的艺术家名称字段以及电影表的电影年份字段。为了连接这两个表，我们使用第三个表 CASTING，使用 Art_id 和 Film_id。加入后，我们在 2016 年至 2018 年间使用“介于”运算符检查电影年份。

```
SELECT A.ART_NAME,  F.FILM_TITLE, F.FILM_YEAR 
FROM ARTIST A, CASTING C, FILMS F
WHERE A.ART_ID=C.ART_ID 
AND C.FILM_ID=F.FILM_ID 
AND F.FILM_YEAR  BETWEEN 2016 AND 2018;
```

**输出:**

<center>

| 艺术名称 | 电影 _ 标题 | 电影 _ 年份 |
| --- | --- | --- |
| AMIT | 战争 2 | Two thousand and seventeen |

**查询-3:**
显示收到明星的电影名称，并根据明星对结果进行排序。

为此，我们需要电影表的电影标题字段以及评论表的星星字段。为了连接这两个表，我们将使用公共字段，即电影标识。在连接之后，我们使用 ORDER BY 子句按照 STARS 递增的顺序显示结果。

```
SELECT F.FILM_TITLE, R_STARS
FROM FILMS F, REVIEW R
WHERE F.FILM_ID=R.FILM_ID
ORDER BY R.STARS DESC
```

**输出:**

<center>

| 电影 _ 标题 | 明星 |
| --- | --- |
| 五月 | five |
| BHANUMATI | four |
| 战争 2 | four |
| 片刻 | Two |

</center>

**查询-4:**
将制片人为‘NIRAJ’的所有电影的主演更新为 5。

首先，我们使用以下查询找到名为“NIRAJ”的生产者的生产者标识:

```
SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’
```

然后使用这个产品标识从电影表中找到电影标识。

```
SELECT FILM_ID FROM FILMS 
WHERE PROD_ID IN (SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’)
```

然后这个电影标识有助于使用更新命令更新评论表中的星星值。

```
UPDATE REVIEW 
SET STARS=5 
WHERE FILM_ID IN (SELECT FILM_ID FROM FILMS 
WHERE PROD_ID IN (SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’));
```

**输出:**

```
1 row updated.
```

要观察这些变化，我们可以使用 REVIEW 表中的 SELECT *命令。

```
SELECT * FROM REVIEW;
```

<center>

| 电影 id | 明星 |
| --- | --- |
| Eleven | four |
| Twelve | five |
| Thirteen | five |
| Fourteen | four |

</center>

</center>