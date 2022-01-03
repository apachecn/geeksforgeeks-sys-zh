# 地点和分组依据之间的差异

> 原文:[https://www . geesforgeks . org/where-and-group-by/](https://www.geeksforgeeks.org/difference-between-where-and-group-by/)之间的差异

先决条件–[WHERE 子句](https://www.geeksforgeeks.org/sql-where-clause/)、 [GROUP BY](https://www.geeksforgeeks.org/sql-group-by/) 、 [Having vs Where 子句](https://www.geeksforgeeks.org/having-vs-where-clause/)
**其中**和 **Group By** 子句用于根据条件筛选查询返回的行。区别如下。

**WHERE 子句**为查询返回的行指定搜索条件，并将行限制在特定的行集内。如果一个表有大量的记录，如果有人想得到特定的记录，那么使用 where 子句是有用的。

**GROUP BY 子句**通过在 SELECT 列表中使用适当的[聚合函数](https://www.geeksforgeeks.org/database-management-system-aggregate-functions/)，如 COUNT()、SUM()、MIN()、MAX()、AVG()等，将相同的行汇总到单个/不同的组中，并返回包含每个组的汇总的单行。

**用例:**
假设某销售公司想得到一份去年购买了一些商品的客户名单，这样他们今年就可以多卖一些东西给他们。
有一个名为 SalesOrder 的表，列有 CustomerId、SalesOrderId、Order_Date、OrderNumber、OrderItem、UnitPrice、OrderQty
现在我们需要得到去年即 2017 年下订单的客户

**使用 Where 子句–**

```
SELECT * 
FROM [Sales].[Orders]
WHERE Order_Date >= '2017-01-01 00:00:00.000'
AND Order_Date < '2018-01-01 00:00:00.000' 
```

这将返回包含 2017 年所有客户和相应订单的行集。

**使用分组依据条款–**

```
SELECT CustomerID, COUNT(*) AS OrderNumbers
FROM [Sales].[Orders]
WHERE Order_Date >= '2017-01-01 00:00:00.000'
AND Order_Date < '2018-01-01 00:00:00.000'
GROUP BY CustomerId 
```

这将返回 2017 年下订单的客户(客户标识)的行集以及每个客户下的订单总数。

**使用 Having 子句–**
Having 子句用于过滤 Group By 子句中的值。下面的查询过滤掉了一些行

```
SELECT SalesOrderID,
         SUM(UnitPrice* OrderQty) AS TotalPrice
FROM     Sales.SalesOrderDetail
GROUP BY SalesOrderID
HAVING   TotalPrice > 5000 
```

因为 WHERE 子句的可见性是一次一行，所以它没有办法计算所有 SalesOrderID 的总和。HAVING 子句在创建分组后计算。

你也可以把 Where 子句和 Having 子句一起使用。WHERE 子句首先应用于表中的各个行。只有满足 WHERE 子句中条件的行才会被分组。然后将 HAVING 子句应用于结果集中的行。

**示例:**

```
SELECT SalesOrderID,
         SUM(UnitPrice * OrderQty) AS TotalPrice
FROM     Sales.SalesOrderDetail
WHERE    SalesOrderID > 500
GROUP BY SalesOrderID
HAVING   SUM(UnitPrice * OrderQty) > 10000 
```

因此，在这里，having 子句将应用于由 where 子句筛选的行。Having 子句只能比较聚合函数的结果或分组的列部分。

**结论:**

1.  **其中**用于在任何分组发生之前过滤记录，即在单行上的*。*
2.  **分组依据**汇总/分组行，并返回每个组的汇总*。*
3.  **HAVING** 用于在值*被分组*后过滤值。