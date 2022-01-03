# 红外系统中的查询类型

> 原文:[https://www . geesforgeks . org/in-IR-system 查询类型/](https://www.geeksforgeeks.org/types-of-queries-in-ir-systems/)

在索引过程中，许多关键字与包含单词、短语、创建日期、作者姓名和文档类型的文档集相关联。它们被一个红外系统用来建立一个倒排索引，然后在搜索过程中参考。将用户制定的查询与索引关键字集进行比较。大多数红外系统还允许使用布尔和其他运算符来构建复杂的查询。带有这些操作符的查询语言丰富了用户信息需求的表现力。

[信息检索(IR)](https://www.geeksforgeeks.org/what-is-information-retrieval/) 系统根据用户查询从大数据集中找到相关文档。用户向搜索引擎提交的查询可能是模糊的、简洁的，其含义可能会随着时间的推移而改变。红外系统中的一些查询类型有–

**1。关键词查询:**

*   Simple and most common queries.
*   Users only need to input keyword combinations to retrieve documents.
*   These keywords are connected by the logical AND operator.
*   All retrieval models support keyword query.

**2。布尔查询:**

*   一些红外系统允许在关键字公式的组合中使用+、-、与、或、非(、)、布尔运算符。
*   不涉及排名，因为文档要么满足这样的查询，要么不满足它。
*   如果在逻辑上与文档完全匹配，则检索文档进行布尔查询。

**3。阶段查询:**

*   When the inverted keyword index is used to represent a document for searching, the relative order of items in the document will be lost.
*   In order to perform accurate phase retrieval, these phases are encoded in the inverted index or implemented in different ways.
*   This query consists of a series of words that make up a stage.
*   Generally enclosed in double quotation marks.

**4。接近度查询:**

*   Proximity refers to the search of how close multiple items in a record should be.
*   The most commonly used proximity search option is stage search, which requires accurate order of terms.
*   Other proximity operators can specify the proximity between terms. Some specify the order of search terms.
*   Search engines use various operator names, such as NEAR, ADJ or AFTER.
*   However, it becomes expensive to provide support for complex proximity operators, because it requires time-consuming document preprocessing, so it is suitable for small document collections, not networks.

**5。通配符查询:**

*   Support regular expression and text search based on pattern matching.
*   The retrieval model does not directly support this query type.
*   In the infrared system, it is possible to support specific kinds of wildcard search. Example: Usually words that end with trailing characters.

**6。自然语言查询:**

*   Only a few natural language search engines are designed to understand the structure and meaning of queries written in natural language texts, usually as questions or narrations.
*   The system tries to formulate answers for these queries from the retrieved results.
*   Semantic model can provide support for this query type.