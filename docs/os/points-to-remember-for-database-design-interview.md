# 数据库设计面试需要记住的要点

> 原文:[https://www . geeksforgeeks . org/为数据库设计面试加分/](https://www.geeksforgeeks.org/points-to-remember-for-database-design-interview/)

在本文中，我们将在采访中讨论一些与数据库设计相关的常见问题。在这里，我们将讨论在面对数据库设计面试时需要牢记的几点。

[数据库设计](https://www.geeksforgeeks.org/significance-of-database-design/)本身就是信息技术行业的完整领域之一。每个信息技术组织在开发应用程序或项目时都会关注数据库设计部分。在这个领域，你可以专门作为一个数据库设计师工作，这在信息技术行业是要求很高的。

对于数据库设计者角色，您必须对数据库设计的基本原理部分有很强的了解。你必须对如何根据客户的特定需求为应用程序设计一个好的数据库模型有很强的知识。

面试官要求[设计数据库](https://www.geeksforgeeks.org/significance-of-database-design/)供自己个人使用。处理这类问题的最佳方法是一步一步地进行，并遵循自上而下的方法，即从更广的视角转向更窄的视角。人们可能还会注意到这种方法和[面向对象设计](https://www.geeksforgeeks.org/oops-object-oriented-design/)方法之间的相似之处。

**1。处理歧义:**

[数据库](https://www.geeksforgeeks.org/dbms/)的问题往往有一些歧义，有意无意。在继续设计之前，你必须确切地了解你需要设计什么。

主要的问题是设计一个系统来代表一个公寓出租机构。现在设计师需要知道这个机构是有多个地点还是只有一个地点。所以求职者也应该和你的面试官讨论一下设计应该有多一般。

例如，一个人在同一栋楼里租两套公寓是极其罕见的。但是这是否意味着设计不能处理这个问题(也许，也许不能)。一些非常罕见的情况可能最好通过变通方法来处理(比如在数据库中复制该人的联系信息)。

**2。定义核心对象:**

接下来，设计人员应该查看需要构建的系统的核心对象。这些核心对象中的每一个通常都转换成一个表。在这种情况下，我们的核心对象可能是物业、建筑、公寓、租户和经理。

**3。分析关系:**

提出的一个主要问题是概述核心对象应该让我们很好地了解表应该是什么。这些表格是如何相互关联的，需要回答它们是多对多还是一对多。

如果建筑物与公寓有一对多的关系(一个建筑物有多个公寓)，那么这可能表示如下。

```
Apartment ID int
ApartmentAddress varchar(100)
BuildingID int
BuildingID int
BuildingName varchar(100)
BuildingAddress varchar(500)
```

**注:**

公寓表链接回带有建筑标识列的建筑。

如果一家公司希望考虑到一个人租一套以上公寓的可能性，设计师可能希望实现如下的多对多关系。

```
TenantApartment's ""
TenantID I int
ApartmentID I int
ApartmentID int
ApartmentAddress varchar(500)
BuildingID int
TenantID int
TenantName varchar(100)
TenantAddress varchar(500)
```

租赁部分表存储了租户和公寓之间的关系。

**4。调查行动:**

最后，设计人员准备将细节填入数据库。演练将采取的常见操作，并了解如何存储和检索相关数据。设计最终结构需要处理租赁条款、迁出、租金支付等。这些操作都需要新的表和列。