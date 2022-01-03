# 数据库管理系统中特定的缓冲区替换策略

> 原文:[https://www . geesforgeks . org/specific-buffer-replacement-policies-in-DBMS/](https://www.geeksforgeeks.org/specific-buffer-replacement-policies-in-dbms/)

在本文中，我们将讨论缓冲区替换策略，还将介绍每个策略的一些特定功能。我们一个一个来讨论。

[DBMS](https://www.geeksforgeeks.org/dbms/) 缓存将保存包含主内存缓冲区中当前正在处理的信息的磁盘页面。如果数据库管理系统缓存中的所有缓冲区都被复制，并且需要将新的磁盘页面从磁盘加载到主内存中，则需要新的页面替换策略来选择要替换的特定缓冲区。

以下是专门为数据库系统开发的一些页面替换策略。

1.  **域分离(DS)方法:**
    DBMS 包含很多磁盘页面，如索引页面、数据文件页面、日志文件页面等。数据库管理系统缓存被划分为独立的域(缓冲区集)。每个域处理一种类型的磁盘页面，每个域内的页面替换通过基本的 LRU(最近最少使用)页面替换来处理。它是一种静态算法，不适应动态变化的负载。本文提出了几种增加动态负载平衡功能的变体。

例如，*GRU*(LRU 组)给每个域一个优先级，并从低优先级域中选择页面，而其他方法根据当前工作负载动态改变每个域中的缓冲区数量。

*   **Hot Set Method :**
    This is useful in queries that have to scan a set of pages repeatedly, such as where a *join* operation is performed using the nested-loop method. If inner loop file is loaded completely into main memory buffers without replacement (the hot set), the join will be performed efficiently because each page in the outer loop file will have to scan all records in the inner loop file to find join matches.

    此方法为每个数据库处理算法集确定将被重复访问的磁盘页，并且在处理完成之前不会替换它们。

    *   **DBMIN 方法:**
    这使用了一个称为 QLSM(查询局部性集合模型)的模型，该模型为特定类型的数据库操作预先确定每个算法的页面引用模式。此方法使用 QLSM 为查询中涉及的每个文件实例计算*位置集*。然后，它根据为该文件实例设置的位置，为查询中涉及的每个文件实例分配适当数量的缓冲区。