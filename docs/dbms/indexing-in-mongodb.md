# 蒙古数据库中的索引

> 原文:[https://www.geeksforgeeks.org/indexing-in-mongodb/](https://www.geeksforgeeks.org/indexing-in-mongodb/)

[MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) 是领先的用 C++编写的 NoSQL 数据库。它具有高可扩展性，并提供高性能和高可用性。它基于集合和文档的概念。MongoDB 中的集合是绑定在一起的一组相关文档。该集合不遵循任何模式，这是 MongoDB 的显著特征之一。

**MongoDB 中的索引:**
MongoDB 使用索引是为了使查询处理更加高效。如果没有索引，那么 MongoDB 必须扫描集合中的每个文档，并且只检索那些与查询匹配的文档。索引是特殊的数据结构，它存储了一些与文档相关的信息，这样 MongoDB 就很容易找到正确的数据文件。索引按索引中指定的字段值排序。

**创建索引:**
MongoDB 提供了一个名为 createIndex()的方法，允许用户创建索引。

**语法–**

```
db.COLLECTION_NAME.createIndex({KEY:1}) 
```

该键决定了要创建索引的字段，1(或-1)决定了这些索引的排列顺序(升序或降序)。

**示例–**

```
db.mycol.createIndex({“age”:1})
{
“createdCollectionAutomatically” : false,
“numIndexesBefore” : 1,
“numIndexesAfter” : 2,
“ok” : 1
} 
```

createIndex()方法还有许多可选参数。
这些包括:

*   背景(布尔型)
*   唯一(布尔型)
*   名称(字符串)
*   稀疏(布尔)
*   删除索引

为了删除索引，MongoDB 提供了 dropIndex()方法。

**语法–**

```
db.NAME_OF_COLLECTION.dropIndex({KEY:1}) 
```

dropIndex()方法一次只能删除一个索引。为了从集合中删除(或删除)多个索引，MongoDB 提供了 dropIndexes()方法，该方法将多个索引作为其参数。

**语法–**

```
db.NAME_OF_COLLECTION.dropIndexes({KEY1:1, KEY2, 1}) 
```

dropIndex()方法一次只能删除一个索引。为了从集合中删除(或删除)多个索引，MongoDB 提供了 dropIndexes()方法，该方法将多个索引作为其参数。

**获取所有索引的描述:**
MongoDB 中的 getIndexes()方法给出了给定集合中存在的所有索引的描述。

**语法–**

```
db.NAME_OF_COLLECTION.getIndexes() 
```

它将检索集合中创建的索引的所有描述。