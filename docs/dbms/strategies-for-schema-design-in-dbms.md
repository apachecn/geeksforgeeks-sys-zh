# 数据库管理系统中的模式设计策略

> 原文:[https://www . geesforgeks . org/strategies-for-schema-design-in-DBMS/](https://www.geeksforgeeks.org/strategies-for-schema-design-in-dbms/)

设计模式时要考虑各种策略。这些策略大多遵循一种增量方法，也就是说，它们必须从需求派生的一些模式结构开始，然后在它们的基础上进行增量修改、细化或构建。让我们讨论其中的一些策略:

1.  **Top-down strategy –** 
    In this strategy, we basically start with a schema that contains a high level of abstraction and then apply successive top-down refinement. Let’s try to understand this with an example, we may specify only a few level entity types and then we specify their attributes split them into lower-level entity types and relationships. The process of specialization to refine an entity type into subclass is also an example of this strategy. 
2.  **Bottom-up strategy –** 
    In this type of strategy, we basically start with basic abstraction and then go on adding to this abstraction. For example, we may start with attributes and group these into entity types and relationships. We can also add a new relationship among entity types as the design goes ahead. The basic example is the process of generalizing entity types into the higher-level generalized superclass. 
3.  **Inside-Out Strategy –** 
    This is a special case of a bottom-up strategy when attention is basically focused on a central set of concepts that are most evident. Modeling then basically spreads outward by considering new concepts in the vicinity of existing ones. We could specify a few clearly evident entity types in the schema and continue by adding other entity types and relationships that are related to each other. 
4.  **Mixed Strategy –** 
    Instead of using any particular strategy throughout the design, the requirements are partitioned according to a top-down strategy, and part of the schema is designed for each partition according to a bottom-up strategy after that various schema are combined.