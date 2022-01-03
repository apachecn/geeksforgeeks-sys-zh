# SQL Server LAG()功能概述

> 原文:[https://www . geesforgeks . org/SQL-server-lag-function-overview/](https://www.geeksforgeeks.org/sql-server-lag-function-overview/)

在许多情况下，用户希望从当前行访问前一行或前一行之前的任何行的数据。
要解决这个问题，可以使用 SQL Server 的 LAG()窗口函数。

**LAG() :**
SQL Server 提供 LAG()函数，该函数在当前行值需要与前一条记录或前一条记录之前的任何记录的数据/值进行比较的情况下非常有用。可以在同一条记录上返回前一个值，而无需使用自连接，从而可以直接进行比较。

**语法:**

```
LAG (scalar_expression [, offset] [, default])  
OVER ( [ partition_by ] order_by )  
```

**其中:**

1.  **标量 _ 表达式–**
    基于指定偏移量返回的值。
2.  **偏移量–**
    从当前行返回并从中获取值的行数。如果未指定，默认值为 1。
3.  **默认值–**
    默认值是偏移量超出分区范围时返回的值。如果未指定默认值，则返回空值。
4.  **over([partition _ by]order _ by)–**
    partition _ by 将 FROM 子句生成的结果集划分为应用了该函数的分区。如果省略 PARTITION BY 子句，函数会将整个结果集视为一个组。默认情况下，order_by 子句按升序排序。

**示例-1:**

```
SELECT Organisation, [Year], Revenue,
LAG (Revenue, 1, 0) 
OVER (PARTITION BY Organisation ORDER BY [Year]) AS PrevYearRevenue  
FROM Org 
ORDER BY Organisation, [Year]; 
```

**输出–**

<center>

| 组织 | 年 | 收入 | prevyearravenue |
| --- | --- | --- | --- |
| abc 新闻 | Two thousand and thirteen | Four hundred and forty thousand | Zero |
| abc 新闻 | Two thousand and fourteen | Four hundred and eighty thousand | Four hundred and forty thousand |
| abc 新闻 | Two thousand and fifteen | Four hundred and ninety thousand | Four hundred and eighty thousand |
| abc 新闻 | Two thousand and sixteen | Five hundred thousand | Four hundred and ninety thousand |
| abc 新闻 | Two thousand and seventeen | Five hundred and twenty thousand | Five hundred thousand |
| abc 新闻 | Two thousand and eighteen | Five hundred and twenty-five thousand | Five hundred and twenty thousand |
| abc 新闻 | Two thousand and nineteen | Five hundred and forty thousand | Five hundred and twenty-five thousand |
| abc 新闻 | Two thousand and twenty | Five hundred and fifty thousand | Five hundred and forty thousand |
| z 新闻 | Two thousand and sixteen | Seven hundred and twenty thousand | Zero |
| z 新闻 | Two thousand and seventeen | Seven hundred and fifty thousand | Seven hundred and twenty thousand |
| z 新闻 | Two thousand and eighteen | Seven hundred and eighty thousand | Seven hundred and fifty thousand |
| z 新闻 | Two thousand and nineteen | Eight hundred and eighty thousand | Seven hundred and eighty thousand |
| z 新闻 | Two thousand and twenty | Nine hundred and ten thousand | Eight hundred and eighty thousand |

</center>

在上面的例子中，我们有两个电视新闻频道，其当前和上一年的收入使用 LAG()函数显示在同一行。正如你所看到的，每一个电视新闻频道的第一条记录都没有前一年的收入，所以它显示默认值为 0。当您想要比较连续期间的值时，此函数在为商业智能报告生成数据时非常有用，例如，年度比较、季度比较或每日比较。

**示例-2:**

```
SELECT Z.*,  (Z.Revenue - z.PrevYearRevenue) as YearonYearGrowth
from (SELECT Organisation, [Year], Revenue,
      LAG (Revenue, 1) 
      OVER (PARTITION BY Organisation ORDER BY [Year] ) AS PrevYearRevenue 
      FROM Org) Z ORDER BY Organisation, [Year]; 
```

**输出–**

<center>

| 组织 | 年 | 收入 | prevyearravenue | 年度增长 |
| --- | --- | --- | --- | --- |
| abc 新闻 | Two thousand and thirteen | Four hundred and forty thousand | 空 | 空 |
| abc 新闻 | Two thousand and fourteen | Four hundred and eighty thousand | Four hundred and forty thousand | forty thousand |
| abc 新闻 | Two thousand and fifteen | Four hundred and ninety thousand | Four hundred and eighty thousand | ten thousand |
| abc 新闻 | Two thousand and sixteen | Five hundred thousand | Four hundred and ninety thousand | ten thousand |
| abc 新闻 | Two thousand and seventeen | Five hundred and twenty thousand | Five hundred thousand | Twenty thousand |
| abc 新闻 | Two thousand and eighteen | Five hundred and twenty-five thousand | Five hundred and twenty thousand | Five thousand |
| abc 新闻 | Two thousand and nineteen | Five hundred and forty thousand | Five hundred and twenty-five thousand | Fifteen thousand |
| abc 新闻 | Two thousand and twenty | Five hundred and fifty thousand | Five hundred and forty thousand | ten thousand |
| z 新闻 | Two thousand and sixteen | Seven hundred and twenty thousand | 空 | 空 |
| z 新闻 | Two thousand and seventeen | Seven hundred and fifty thousand | Seven hundred and twenty thousand | thirty thousand |
| z 新闻 | Two thousand and eighteen | Seven hundred and eighty thousand | Seven hundred and fifty thousand | thirty thousand |
| z 新闻 | Two thousand and nineteen | Eight hundred and eighty thousand | Seven hundred and eighty thousand | One hundred thousand |
| z 新闻 | Two thousand and twenty | Nine hundred and ten thousand | Eight hundred and eighty thousand | thirty thousand |

</center>

在上面的例子中，我们可以类似地计算电视新闻频道的同比增长。此外，在这个例子中需要注意的一点是，我们没有向 LAG()提供任何默认参数，因此 LAG()函数返回空值，以防没有以前的值。

LAG()功能可以在数据库级别实现，像 Power BI 和 Tableau 这样的 BI 报告解决方案可以避免在报告层使用繁琐的措施。