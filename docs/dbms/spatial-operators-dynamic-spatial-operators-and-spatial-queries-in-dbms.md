# DBMS 中的空间算子、动态空间算子和空间查询

> 原文:[https://www . geesforgeks . org/spatial-operators-dynamic-spatial-operators-and-spatial-query-in-DBMS/](https://www.geeksforgeeks.org/spatial-operators-dynamic-spatial-operators-and-spatial-queries-in-dbms/)

**1。空间运算符:**
**空间运算符**这些运算符应用于对象的**几何属性**。
然后在物理空间中使用它来捕捉它们以及它们之间的关系。
也用于进行空间分析。

空间运算符分为三类:

1.  **Topological operators :**
    Topological properties do not vary when topological operations are applied, like translation or rotation.

    拓扑算子在许多层次上是分层结构的。基本层为操作员提供了检查宽边界区域之间详细拓扑关系的能力。更高的级别提供了更抽象的操作符，允许用户独立于几何数据模型查询不确定的空间数据。

    **示例–**
    打开(区域)、关闭(区域)和内部(点、环)。

2.  **Projective operators :**
    Projective operators, like convex hull are used to establish predicates regarding the concavity convexity of objects.

    **示例–**
    具有物体内部的凹度。

3.  **Metric operators :**
    Metric operators’s task is to provide a more accurate description of the geometry of the object. They are often used to measure the global properties of singular objects, and to measure the relative position of different objects, in terms of distance and direction.

    **示例–**
    (弧的)长度和(点到点的)距离。

    **2。动态空间操作符:**
    动态操作改变操作符所应用的对象。创建、销毁和更新是基本的动态操作。

    **示例–**
    通过**向上移动空间对象平移**、**旋转**、**向上缩放或向下缩放**、**反射**和**剪切**。

    **3。[空间查询](https://www.geeksforgeeks.org/types-of-spatial-queries-in-dbms/) :**
    对需要使用空间操作的空间数据的请求称为空间查询。

    它可以分为–

    1.  **Range queries :**
        It finds all objects of a particular type that are within a given spatial area.

        **示例–**
        查找西里古里地区的所有医院。这个查询的一个变体是对于给定的位置，查找特定距离内的所有对象，例如，查找 5 公里范围内的所有银行。

    2.  **Nearest neighbor queries :**
        It Finds object of a particular type which is nearest to a given location.

        **示例–**
        找到离事故地点最近的派出所。

    3.  **Spatial joins or overlays :**
        It joins the objects of two types based on spatial condition, such as the objects which are intersecting or overlapping spatially.

        **示例–**
        在两个城市之间的国道上找到所有的达巴斯。它在空间上将乡镇对象和公路对象连接起来。

        查找火车站 5 公里范围内的所有酒店。它在空间上连接火车站对象和酒店对象。