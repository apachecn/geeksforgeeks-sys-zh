# 【DBMS 和 DSMS 的区别

> 原文:[https://www . geesforgeks . org/DBMS 和 dsms 之间的差异/](https://www.geeksforgeeks.org/difference-between-dbms-and-dsms/)

**1。**[**DBMS**](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)**:**
在 DBMS 中，数据的本质是非易失性的，使用 DBMS 执行随机数据访问。它对一次性查询进行操作，并给出该查询的准确输出。数据库管理系统使用无限的二级存储来存储数据，而且在数据库管理系统中，数据更新率非常低。当很少或没有时间要求时，使用数据库管理系统。

**数据库管理系统的应用:**

*   大学记录
*   供应链管理
*   人力资源管理
*   电信记录
*   铁路预订系统

下面的查询是 DBMS 查询的一个**例子，这是一个一次性的查询，给出了确切的答案。**

```
SELECT Name, Role, City
FROM Employees
WHERE City = 'Bhubaneswar'
ORDER BY Name

```

上面的查询是一个非常简单的查询，它显示了其城市属于不丹王国内的公司员工的姓名、角色、城市，输出/结果将按员工的姓名排序。

**2。DSMS :**
在 DSMS，数据的本质是易失性数据流，使用 DSMS 执行顺序数据访问。它对连续查询进行操作，并给出该查询的精确/近似输出。数据库管理系统使用有限的主内存来存储数据，而且在 DSMS，数据更新率非常高。当有实时要求时，使用 DSMS。

**DSMS 的申请:**

*   传感器网络
*   网络流量分析
*   金融出票人
*   在线拍卖
*   事务日志分析

下面的查询是 DSMS 查询的一个**例子，它是一个连续的查询，给出了精确/近似的答案。**

```
SELECT Stream
Rowtime
MIN(Temp) Over W1 as Wmin_temp,
MAX(Temp) Over W1 as Wmax_temp,
AVG(Temp) Over W1 as Wavg_temp,
FROM Wheatherstream
Window W1 as (RANGE INTERVAL '2' SECOND PRECEDING);

```

上述查询聚集了来自天气监测系统的传感器流。然后，它汇总收集的最低、最高和平均温度值。Window 子句创建一个持续时间为 2 秒(指延迟，可以更改)的窗口，显示零结果延迟的增量更新结果流。

**DBMS 和 DSMS 的区别:**

<center>

| 没有。 | 数据库管理系统 | DSMS |
| 01. | 数据库管理系统是指数据库管理系统。 | DSMS 提到数据流管理系统。 |
| 02. | 数据库管理系统处理持久数据。 | 数据流管理系统处理流数据。 |
| 03. | 在数据库管理系统中，会发生随机数据访问。 | 在 DSMS，发生顺序数据访问。 |
| 04. | 它基于查询驱动的处理模型，即所谓的基于拉的模型。 | 它基于数据驱动处理模型，即所谓的基于推送的模型。 |
| 05. | 在数据库管理系统中，查询计划在开始/固定时进行优化。 | DSMS 基于自适应查询计划。 |
| 06. | 数据库管理系统中的数据更新率相对较低。 | DSMS 的数据更新率相对较高。 |
| 07. | 在数据库管理系统中，查询是一次性查询。 | 但在 DSMS，这种质疑是持续不断的。 |
| 08. | 在数据库管理系统中，查询给出了确切的答案。 | 在 DSMS，这个问题给出了确切/近似的答案。 |
| 09. | 数据库管理系统不提供实时服务。 | DSMS 提供实时服务。 |
| 10. | 数据库管理系统使用无界磁盘存储意味着无限的二级存储。 | DSMS 使用有限主存意味着有限主存。 |

</center>