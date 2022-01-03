# Neo4j 查询密码语言

> 原文:[https://www.geeksforgeeks.org/neo4j-query-cypher-language/](https://www.geeksforgeeks.org/neo4j-query-cypher-language/)

Neo4j 有自己的查询语言，叫做 Cypher Language。它类似于 SQL，记住一件事，Neo4j 不处理表、行或列，它处理节点。以图形格式而不是表格格式查看数据更令人满意。

**示例:**Neo4j Cypher 语句与 SQL
进行比较

```
MATCH (G:Company { name:"GeeksforGeeks" })
RETURN G
```

这个密码语句将返回“公司”节点，其中“名称”属性是 GeeksforGeeks。这里的“G”就像一个变量，保存着您的 Cypher 查询需要的数据，之后它将返回。如果你懂 SQL，会更清楚。下面同样的查询是用 SQL 写的。

```
SELECT * FROM Company WHERE name = "GeeksforGeeks";
```

neo4j 是为 NoSQL 数据库设计的，但它在关系数据库上也非常有效，它不使用 SQL 语言。

**ASCII-Art 语法:**Neo4j 使用 **ASCII-Art** 来创建模式。

```
(X)-[:GeeksfroGeeks]->(Y)
```

*   在 Neo4j 中，节点用“()”表示。
*   关系用“->”表示。
*   节点之间是什么样的关系用“[ ]”表示，如[:GeeksforGeeks]

所以上面的描述有助于解码给定的 **ASCII-Art 语法**，*(X)-[:GeeksfroGeeks]->(Y)*。这里的 X 和 Y 是节点 X 对 Y 的关系类是“极客伪造”。

**定义数据:**以下几点有助于你掌握 Cypher 语言的概念。

*   Neo4j 处理节点，节点包含的标签可以是“人”、“员工”、“雇主”任何可以定义值域类型的东西。
*   Neo4j 也有类似“姓名”、“员工 id”、“电话号码”这样的属性，基本上它会给我们关于节点的信息。
*   Neo4j 的关系也可以包含属性，但这不是强制性的。
*   在 Neo4j 中，这种关系就像是 X 为 GeeksforGeeks 工作的那种情况，在这里，X 和“GeeksforGeeks”是节点，这种关系是为工作的，在 Cypher 语言中，它会是这样的。

```
 (X)-[:WORK]->(GeekfoGeeks).
```

**注意:**这里的公司是节点的标签，名称是节点的属性

```
MATCH (G:Company { name:"GeeksforGeeks" })
RETURN G 
```