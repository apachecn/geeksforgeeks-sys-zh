# 统计数据库安全性

> 原文:[https://www . geesforgeks . org/statistical-database-security/](https://www.geeksforgeeks.org/statistical-database-security/)

**先决条件–**[数据库安全控制方法](https://www.geeksforgeeks.org/control-methods-of-database-security/)

某些数据库可能包含国家/地区个人的机密或秘密数据，如(Aadhar 号码、PAN 卡号)，攻击者不得访问该数据库。因此，应该保护它不被用户访问。

包含大量人口详细信息的数据库称为统计数据库，主要用于产生各种人口的统计数据。但是允许用户检索某些人口统计信息，如特定州/地区的人口平均值等，以及它们的总和、计数、最大值、最小值和标准偏差等。

监控统计数据库安全是道德黑客的责任统计用户不允许访问个人数据，如数据库中特定人员的收入、电话号码、特定人员的借记卡号码，因为统计数据库安全技术禁止检索个人数据。数据库管理系统也有责任为个人数据保密。

**统计查询:**
只允许[聚合函数](https://www.geeksforgeeks.org/aggregate-functions-in-sql/)如 COUNT、SUM、MIN、MAX、AVERAGE 和 STANDARD DEVIATION 的查询称为统计查询。统计查询主要用于了解人口统计数据，用于公司/行业维护员工数据库等。

**示例–**
考虑以下统计查询示例，其中 EMP_SALARY 是包含公司每个员工收入的机密数据库。

**查询-1:**

```
SELECT COUNT(*) 
FROM EMP_SALARY
WHERE Emp-department = '3';
```

**查询-2:**

```
SELECT AVG(income) 
FROM EMP_SALARY 
WHERE Emp-id = '2'; 
```

在这里，**“Where”**条件可以被攻击者操纵，如果知道特定员工的 id/姓名，就有机会访问员工个人的收入或员工的机密数据。

通过使用以下措施，减少了从统计查询中获取个人信息的可能性–

1.  **Partitioning of Database –** This means the records of database must be not be stored as bulk in single record. It must be divided into groups of some minimum size according to confidentiality of records.

    数据库分区的优点是查询可以引用任何完整的组或组集，但查询不能访问组内的记录子集。因此，攻击者最多只能访问一两个不太私密的组。

2.  如果选择条件指定的群体中元组的数量低于某个阈值，则不允许进行统计查询。
3.  禁止重复引用相同元组的查询序列。