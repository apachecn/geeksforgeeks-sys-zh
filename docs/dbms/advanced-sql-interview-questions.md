# 高级 SQL 面试问题

> 原文:[https://www . geesforgeks . org/advanced-SQL-面试-问题/](https://www.geeksforgeeks.org/advanced-sql-interview-questions/)

不同的公司有不同的面试方法。有些人会专注于工作经验和知识；其他人可能专注于个性，而其他人则介于两者之间。

因此，从不同的面试问题和答案中发现和学习，有助于从不同的角度了解在不同的市场中什么可能是最重要的。因此，这里有一个基于区块链的电子学习平台的高级 SQL 面试问题列表。

*   **Que-1:** Explain the meaning of ‘index’.
    **Explanation:**
    Indexes help retrieve information from the database faster and with higher efficiency. In other words, it’s a method that enhances performance and there are 3 types of indexes:
    *   **聚集**–使用键值对表格进行重新排序并搜索信息
    *   **非集群**–保持表格的顺序
    *   **唯一**–禁止字段具有重复值

    而且，一个表可以有多个非聚类索引，但只能有 **1** 个单聚类索引。

*   **Que-2:** You forgot your root password, what do you do ?
    **Explanation:**
    1.  用“**跳过-授权-表**的命令启动数据库。
    2.  设置新密码后，以正常模式重新启动数据库并输入新密码。
*   **Que-3:** Are NULL values equal to a zero ?
    **Explanation:**
    No, because a “**zero**” has a numerical manner and **NULL** represent the absence of a character. This happens when the character is unknown or unavailable. Additionally, NULL shouldn’t be confused with **blank space** because data record without any value assigned is not the same as a plain blank space, with no data records attached.
*   **Que-4:** Data disk gets overloaded, what do you do ?
    **Explanation:**
    You should apply a *soft link*: these links create a location where you are able to store your **.frm** and **.idb** files. This will resolve the overload problem.
*   **Que-5:** Explain what‘auto increment’ is?
    **Explanation:**
    This command allows you to generate a unique number when a new record is written to a table. When you want to the **primary key** field value to be generated automatically each time you insert a new record, this is when this function comes in handy.

    另外值得注意的是，该命令可以在各种平台上使用。对于 SQL Servers 来说，“**自动递增**”命令是“**标识**”。

*   **Que-6:** What are the most basic MySQL architecture components ?
    **Explanation:**
    There are three main components:
    1.  查询优化器；
    2.  连接管理器；
    3.  可插拔引擎。
*   **Que-7:** Using an existing table, make an empty one.
    **Explanation:**

    ```
    Select * into employeecopy from employee where 1=2 
    ```

*   **Que-8:** How would you check your current SQL version ?
    **Explanation:**
    You can get the most current SQL version by issuing this command:

    ```
    SELECT VERSION()
    ```

*   **Que-9:** Get alternative odd records from the table.
    **Explanation:**
    This can be achieved using the command:

    ```
    Select employeeId from (Select rowno, employeetId from employee) where mod(rowno, 2)=1 
    ```

*   **Que-10:** 什么命令会从表中选择唯一的记录？
    **解说:**
    的“**泾渭分明**的命令。这里有一个例子:

```
Select DISTINCT employeeID from Employee 
```

*   **Que-11:** What are variables of SQL ?
    **Explanation:**
    In SQL, there are two different variables:
    *   **局部**–这些变量只能存在于单个函数中
    *   **全局**–与局部相反，这意味着它们可以通过整个程序定位。*   **Que-12:** What is a ‘datawarehouse’ and what it does ?
    **Explanation:**
    A “**datawarehouse**” is a system used for data analysis and reporting. Basically, it’s a warehouse of data. Data in DWs can be stored from various areas and sources and thus makes them central repositories of integrated data that is ready for usage.*   **Que-13:** For what ‘recursive stored procedure’ is mainly used ?
    **Explanation:**
    A **recursive stored procedure** is a procedure that will make the code calls itself until specific boundary condition is reached. This is a productivity type of thing, that allows programmers to use the same code a number of times.*   **Que-14:** Retrieve the first 3 characters from a character string.
    **Explanation:**
    There are a few ways to do this. Nevertheless, the command presented below can be treated as a more popular and easier one:

    ```
    Select SUBSTRING(EmployeeSurname, 1, 5) as employeesurname from employee 
    ```

    *   **Que-15:** 如何从两个表中检索常用记录？
    **解释:**
    通过执行以下任务:

    ```
    Select employeeID from employee. INTERSECT Select EmployeeID from WorkShift 
    ```