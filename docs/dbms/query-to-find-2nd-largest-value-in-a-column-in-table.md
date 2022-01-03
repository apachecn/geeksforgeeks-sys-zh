# 查询查找表

中某一列的第二大值

> 原文:[https://www . geesforgeks . org/query-to-find-表中第二大列值/](https://www.geeksforgeeks.org/query-to-find-2nd-largest-value-in-a-column-in-table/)

**问题:**编写一个 SQL 查询来查找表中某列的第二大值。

**示例:**
在第一个示例中，在“收入”列中查找第二大值，在第二个示例中，在“成本”列中查找第二大值。

```
Input: Table name- Employee
+------+--------+
| Name | Income |
+------+--------+
| abc  | 4000   |
| xyz  | 4752   |
| qwe  | 6579   |
+------+--------+

Output: 4752

Input: Table name- price_list
+-------------+--------+
| Item        | Cost   |
+-------------+--------+
| Apple       | 150    |
| Banana      | 175    |
| Mango       | 200    |
| Pineapple   | 180    |
+-------------+--------+

Output: 180 
```

**方法-1:**

**语法:**

```
SELECT MAX (column_name) 
FROM table_name 
WHERE column_name NOT IN (SELECT Max (column_name) 
                          FROM table_name); 
```

首先，我们从表中的该列中选择最大值，然后我们在该列中再次搜索最大值，排除已经找到的最大值，因此得到第二个最大值。

*   **示例-1:**

    ```
    SELECT MAX (Income) 
    FROM Employee 
    WHERE Salary NOT IN (SELECT Max (Income) 
                         FROM Employee); 
    ```

*   **示例-2:**

    ```
    SELECT MAX (Cost) 
    FROM price_list 
    WHERE Salary NOT IN (SELECT Max (Cost) 
                         FROM price_list); 
    ```

**方法-2:**

**语法:**

```
SELECT column_name
FROM table_name e
WHERE 2 = (SELECT COUNT (DISTINCT column_name) 
           FROM table_name p
           WHERE e.column_name<=p.column_name) 
```

这是一个嵌套子查询，它是一个通用的 SQL 查询，用于打印列中的第 n 个最大值。对于由外部查询处理的每条记录，将执行内部查询，并将返回有多少条记录的值小于当前值。如果您正在寻找第二高的值，那么一旦内部查询返回 2，您的查询就会停止。

*   **示例-1:**

    ```
    SELECT Income
    FROM Employee e
    WHERE 2=(SELECT COUNT(DISTINCT Income) 
             FROM Employee p
             WHERE e.Income<=p.Income) 
    ```

*   **示例-2:**

    ```
    SELECT Cost
    FROM price_list e
    WHERE 2=(SELECT COUNT(DISTINCT Cost) 
             FROM price_list p
             WHERE e.Cost<=p.Cost) 
    ```