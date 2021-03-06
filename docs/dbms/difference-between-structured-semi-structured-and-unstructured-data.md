# 结构化、半结构化和非结构化数据的区别

> 原文:[https://www . geesforgeks . org/结构化-半结构化和非结构化数据的区别/](https://www.geeksforgeeks.org/difference-between-structured-semi-structured-and-unstructured-data/)

**大数据**包括海量、高速、可扩展的各种数据。这是 3 种类型:结构化数据、半结构化数据和非结构化数据。

1.  **结构化数据–**
    结构化数据是其元素可寻址以进行有效分析的数据。它被组织成一个格式化的存储库，通常是一个数据库。它涉及可以存储在带有行和列的表中的数据库 SQL 中的所有数据。它们有关系键，可以很容易地映射到预先设计的字段中。如今，这些数据大多是在开发过程中处理的，也是管理信息最简单的方式。*示例:*关系数据。

2.  **半结构化数据–**
    半结构化数据是不驻留在关系数据库中的信息，但具有一些组织属性，使其更易于分析。对于某些流程，您可以将它们存储在关系数据库中(对于某种半结构化数据来说，这可能非常困难)，但是半结构化的存在是为了节省空间。*示例* : XML 数据。

3.  **非结构化数据–**
    非结构化数据是指没有按照预先定义的方式组织或者没有预先定义的数据模型的数据，因此不太适合主流的关系数据库。因此，对于非结构化数据，有存储和管理的替代平台，它在信息技术系统中日益普遍，并被组织用于各种商业智能和分析应用。*示例*:文字、PDF、文字、媒体日志。

**结构化、半结构化和非结构化数据的区别:**

<figure class="table">

| 性能 | 结构数据 | 半结构化数据 | 非结构化数据 |
| --- | --- | --- | --- |
| 技术 | 它基于关系数据库表 | 它基于 XML/RDF(资源描述框架)。 | 它基于字符和二进制数据 |
| 事务管理 | 成熟的事务和各种并发技术 | 事务是从未成熟的数据库管理系统改编而来的 | 没有事务管理和并发性 |
| 版本管理 | 元组、行、表的版本控制 | 元组或图的版本控制是可能的 | 整体版本化 |
| 灵活性 | 它依赖于模式，不太灵活 | 它比结构化数据更灵活，但不如非结构化数据灵活 | 它更灵活，而且没有模式 |
| 可量测性 | 扩展数据库模式非常困难 | 它的扩展比结构化数据更简单 | 它更具可扩展性。 |
| 稳健性 | 非常健壮 | 新技术，不是很普及 | — |
| 查询性能 | 结构化查询允许复杂连接 | 匿名节点上的查询是可能的 | 只有文本查询是可能的 |

</figure>