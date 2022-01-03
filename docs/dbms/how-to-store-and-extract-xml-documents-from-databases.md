# 如何从数据库中存储和提取 XML 文档

> 原文:[https://www . geesforgeks . org/如何从数据库中存储和提取 xml 文档/](https://www.geeksforgeeks.org/how-to-store-and-extract-xml-documents-from-databases/)

我们可以使用不同的方法来组织 XML 文档的内容，以便于后续的查询和检索。

以下是从数据库中存储和提取 XML 文档的方法。

1.  In the first approach, we can use database management system in which we store the document as a text and the relational and object DBMS are used to store XML whole document as a text field in the DBMS record and object. In this process, we can use document processing for Database management system as a special module and its store schemaless and document-centric XML document.
2.  In the second approach again we use Database Management System but this time we can use for storing document content as data element .this process follows XML or XML DTD schema and all the document have the same structure in which we can design a relational object database to store the leaf-level data element in the XML document. For this, we required a mapping algorithm to design a schema for a database that is compatible with XML document structure.

    它通常用于从为 XML 或 DTD 模式指定的存储数据中重新创建 XML 文档。这有助于实现不属于数据库管理系统的内部数据库管理系统模块或中间件。

3.  In the third approach, we can use different type Database management system which is based on a hierarchical(tree) model for designed and implemented and designing a master system for storing native XML data. This system is also called as native XML DBMS and In this process, the system may involve indexing and querying techniques which is work for all types of an XML document.

    它可能包括数据压缩技术，该技术被高度用于减小存储文档的大小。有各种软件提供原生的可扩展标记语言存储选项，如动态应用平台的 Tamino 软件公司或 Excelon 提供原生的可扩展标记语言数据库管理系统功能，oracle 也提供原生的可扩展标记语言存储选项。

4.  In the fourth approach, we can create and customized [XML document](https://www.geeksforgeeks.org/xml-basics/) and publishing from pre-existing relational database Because relational database already stored huge amount of data which is a part of data in which we need to formatted data as a document for displaying into the web or exchanging.

    这个过程用于划分中间件软件层，以调整一个 XML 文档和关系数据库之间的转换。