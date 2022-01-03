# 数据库管理系统中空间查询的类型

> 原文:[https://www . geeksforgeeks . org/DBMS 中的空间查询类型/](https://www.geeksforgeeks.org/types-of-spatial-queries-in-dbms/)

任何类型的空间数据，即与位置相关的数据和表示几何空间中定义的对象的数据，都由**空间数据库**存储和维护。这些用于处理这些空间数据库。空间数据库主要包含简单几何对象的表示，如三维对象、拓扑覆盖、线性网络和不规则三角网。

空间查询主要有**三种**类型，如下所示。

1.  **Nearness queries:**
    It request objects that present near a specified location. A query to find all Hotels that lie within a given distance of a given point is an example of a nearness query. The nearest-neighbor query requests the object that is nearest to a specified point.

    例如，我们可能想找到最近的火车站。请注意，该查询不必指定距离限制，因此即使我们不知道最近的火车站有多远，我们也可以询问它。

2.  **区域查询:**
    处理空间区域。例如，查询可以要求部分或全部出现在固定区域内的对象
    。查询一个特定城镇地理范围内的所有药店，或者我们可以找到特定城市的所有学校。
3.  **Union/Intersection:**
    In this type of queries, we may also request intersections and unions of regions.

    例如，给定区域信息，例如年降雨量和人口密度，查询可以请求年降雨量低和人口密度高的所有区域。

一般来说，在空间数据的查询中有**空间需求和**非空间需求的组合。例如，我们可能想找到最近的餐馆，那里有素食选择，每顿饭收费不到 10 美元。

由于空间数据本质上是图形化的，我们通常使用**图形查询语言**进行查询。此类查询的结果也以图形方式显示，而不是以表格形式显示。用户可以在界面上调用各种操作，例如选择要查看的区域(例如，通过指向和点击曼哈顿以西的郊区)、放大和缩小、基于选择条件选择要显示的内容(例如，具有超过三颗星的酒店)、叠加多个地图(例如，具有超过三颗星的酒店叠加在表示低犯罪率区域的地图上)等等。图形界面构成了前端。

已经提出了 SQL 的扩展，以允许关系数据库有效地存储和检索空间信息，并且还允许查询混合空间和非空间条件。扩展包括允许抽象数据类型，如线、面和位图，以及允许空间条件，如包含或重叠。