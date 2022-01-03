# 在 SQL Server 中将行组合成字符串

> 原文:[https://www . geesforgeks . org/combine-row-in-string-SQL-server/](https://www.geeksforgeeks.org/combine-rows-into-string-in-sql-server/)

假设我们需要从任何给定的列表中选择所有的数据。我们可以使用多个查询将 SQL Server 中的行组合成一个字符串。

**示例-1 :**
假设我们有一个名为“ **geek_demo** ”的下表–

<figure class="table">

| 西方人名的第一个字 | 姓 | 薪水 | 城市 |
| --- | --- | --- | --- |
| 鸭子！鸭子 | 笈多王朝 | Twenty-four thousand five hundred | 德里 |
| 巴比塔 | 达达塔 | Twenty-three thousand six hundred | 无聊死了 |
| 车坛 | 耆那教教徒 | Twenty-five thousand six hundred | 无聊死了 |
| 迪帕克（男子名） | 赛尼 | Twenty-four thousand three hundred | 德里 |
| 伊莎！伊莎 | 夏尔马 | Twenty-five thousand nine hundred | 德里 |
| 库希 | 辛格 | Twenty-four thousand six hundred | 无聊死了 |
| 非常 | 戈亚尔 | Twenty-five thousand five hundred | 无聊死了 |
| 毛 | 活女神 | Twenty-three thousand nine hundred | 无聊死了 |

**Approach-1 :**
在下面的例子中，我们将使用聚结函数合并行。

**查询连接 SQL Server 中的行–**

```
DECLARE @Names VARCHAR(MAX)  
SELECT @Names = COALESCE(@Names + ', ', '') + [FirstName] 
FROM [geek_demo]
SELECT @Names AS [List of All Names]
```

**输出:**

<figure class="table">

| 所有名称列表 |
| --- |
| 安提、巴比塔、切特、迪皮卡、伊莎、赫希、梅哈、帕尔 |

**Approach-2 :**
在下面的例子中，我们也将组合姓氏行。

**查询连接 SQL Server 中的行–**

```
DECLARE @FirstNames VARCHAR(MAX)
DECLARE @LastNames VARCHAR(MAX)
SELECT @FirstNames = COALESCE(@FirstNames + ', ', '') + [FirstName] 
FROM [geek_demo]   
SELECT @LastNames = COALESCE(@LastNames + ', ', '') + [LastName] 
FROM [geek_demo] 
SELECT @FirstNames AS [List of All First Names],
            @LastNames AS [List of All Last Names]
```

**输出:**

<figure class="table">

| 所有名字的列表 | 所有姓氏列表 |
| --- | --- |
| 安提、巴比塔、切特、迪皮卡、伊莎、赫希、梅哈、帕尔 | 古普塔、杜塔、贾恩、赛尼、夏尔马、辛格、戈亚尔、活女神 |

**方法-3 :**
在下面的例子中，我们也将连接姓氏行。

**查询连接 SQL Server 中的行–**

```
DECLARE @FirstNames VARCHAR(MAX)
DECLARE @LastNames VARCHAR(MAX)
SELECT @FirstNames = CONCAT(@FirstNames + ', ', '') + [FirstName] 
FROM [geek_demo]  
SELECT @LastNames = CONCAT(@LastNames + ', ', '') + [LastName] 
FROM [geek_demo]
SELECT @FirstNames AS [List of First All Names],
   @LastNames AS [List of All Last Names]
```

**输出:**

<figure class="table">

| 名字列表 | 所有姓氏列表 |
| --- | --- |
| 安提、巴比塔、切特、迪皮卡、伊莎、赫希、梅哈、帕尔 | 古普塔、杜塔、贾恩、赛尼、夏尔马、辛格、戈亚尔、活女神 |

**Approach-4 :**
在下面的例子中，我们将使用 stuff 函数结合两列(名字&姓氏)的行，并用于 XML 路径。

**查询连接 SQL Server 中的行–**

```
SELECT STUFF((
   SELECT ',' + SPACE(1) + [FirstName],
   ' ' + SPACE(1) + [LastName]
 FROM [geek_demo]
  FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
AS [List Of All Names]
```

**输出:**

<figure class="table">

| 姓名列表 |
| --- |
| Ankit Gupta、Babita Dutta、Chetan Jain、deepka saini、Isha Sharma、Khushi Singh、Megha Goyal、Parul Kumari |

**示例-2 :**
让我们假设我们有一个名为**“geek _ demo 1”**–

<figure class="table">的下表

| 名字 | 加入日期 | 电子邮件 |
| --- | --- | --- |
| 鸭子！鸭子 | 2018 年 5 月 4 日 | ankit@gfg.org |
| 巴比塔 | 2019 年 7 月 9 日 | babita@gfg.org |
| 车坛 | 2017 年 6 月 14 日 | chetan@gfg.org |
| 迪帕克（男子名） | 2019 年 1 月 26 日 | deepak@gfg.org |
| 伊莎！伊莎 | 2018 年 5 月 24 日 | 伊莎@gfg.org |
| 库希 | 2018 年 7 月 17 日 | khushi@gfg.org |
| 非常 | 2017 年 3 月 3 日 | megha@gfg.org |
| 毛 | 2018 年 12 月 20 日 | parul@gfg.org |

**方法-1 :**
在下面的例子中，我们将使用 SQL Server 中的 CONCAT 函数将行组合成一个字符串。

**查询连接 SQL Server 中的行–**

```
DECLARE @Names VARCHAR(MAX)
DECLARE @Emails VARCHAR(MAX)
SELECT @Names = CONCAT(@Names + ', ', '') + [Name] 
FROM [geek_demo1]  
SELECT @Emails = CONCAT(@Emails + ', ', '') + [Email] 
FROM [geek_demo]  
SELECT @Names AS [List of All Names],
            @Emails AS [List of All Emails]
```

**输出:**

<figure class="table">

| 所有名称列表 | 所有电子邮件列表 |
| --- | --- |
| 安提、巴比塔、切特、迪皮卡、伊莎、赫希、梅哈、帕尔 | ankit@gfg.org、babita@gfg.org、chetan@gfg.org、deepak@gfg.org、isha@gfg.org、khushi@gfg.org、megha@gfg.org、parul@gfg.org |

**方法-2 :**
在下面的示例中，我们将使用 SPACE 和 for XML 路径组合 SQL Server 中的行。

**查询连接 SQL Server 中的行–**

```
SELECT STUFF((
  SELECT ',' + SPACE(1) + [Email]
  FROM [geek_demo]
  FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
AS [List Of All Emails]
```

**输出:**

<figure class="table">

| 所有电子邮件列表 |
| --- |
| ankit@gfg.org、babita@gfg.org、chetan@gfg.org、deepak@gfg.org、isha@gfg.org、khushi@gfg.org、megha@gfg.org、parul@gfg.org |

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>