# Neo4j |值和类型

> 原文:[https://www.geeksforgeeks.org/neo4j-values-and-types/](https://www.geeksforgeeks.org/neo4j-values-and-types/)

Neo4j 通过 Cypher 语言工作，Cypher 语言为许多数据类型提供一流的支持。所有的数字数据类型都属于不同的类别，这将在下面用这些类别的小节进行描述。

**Neo4j 中的数据类型:**
有:属性类型、结构类型和复合类型。这些解释如下。

1.  **Property Types:**
    The Neo4j property types can be returned by cypher queries, can be used as a parameters, also can be stored as properties and can be constructed with Cypher literals.

    **属性类型由:**组成

    *   Number，一个抽象类型，它有整数和浮点两个子类型
    *   线
    *   布尔代数学体系的
    *   空间类型点
    *   时间类型:日期、时间、本地时间、日期时间、本地日期时间和持续时间

    形容词数字用于描述 Cypher 函数或表达式。它表示任何类型的数字(整数或浮点数)都适用。所有简单类型的同类列表都可以存储为属性，但一般列表(复合类型)不能存储。cypher 语言还为字节数组提供了传递支持，字节数组可以存储属性值，但没有文字表示。

    **特殊字符排序:**
    包含不属于的特殊字符的 Neo4j 字符串(BMP 代表基本多语言平面)可以有不一致的排序。
    **注:** BMP 是 Unicode 定义的所有字符的子集(通用语言的通用字符)。那些不属于 BMP，它们属于补充多语言平面或补充表意平面。

2.  **Structural Types:**
    It can be returned by cypher queries, can’t used as a parameters, also can’t stored as properties and can’t constructed with Cypher literals.

    **结构类型由:**
    组成，包含**节点**、**关系**和**路径**。节点由 *id* 、*标签*和*地图*组成，每个节点用圆圈表示，所有创建地图并属于标签的节点都可以连接起来。关系由开始节点和结束节点的 *Id* 、*类型*、*映射*和*Id*组成。最后一条路径由节点和关系的交替序列组成。

    **注意:**作为模式匹配的结果，返回所有的节点、关系和路径。请记住，标签不是值，它们是模式语法的形式。

3.  **Composite Types:**
    The Neo4j Composite types can be returned by cypher queries, can be used as a parameters, also can’t stored as properties and can be constructed with Cypher literals.

    合成类型有**列表**和**地图**。

    *   **列表:**
        所有列表都是异构的、有序的值集合，每个值都有任何种类的属性、结构或复合类型。
    *   **映射:**
        映射是(键、值)对的异构、无序集合，其中键是字符串，值具有任何属性、结构或复合类型。

**参考:**[https://neo4j . com/docs/cypher-manual/current/语法/values/# composite-type](https://neo4j.com/docs/cypher-manual/current/syntax/values/#composite-types)