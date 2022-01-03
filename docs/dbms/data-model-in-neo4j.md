# Neo4j 中的数据模型

> 原文:[https://www.geeksforgeeks.org/data-model-in-neo4j/](https://www.geeksforgeeks.org/data-model-in-neo4j/)

*Neo4j* 中的数据模型使用节点和关系的概念来组织数据。节点和关系都可以有属性，这些属性存储与节点和关系相关联的数据项。

节点可以有**标签**:

*   一个节点可以有零个、一个或多个标签。
*   具有相同标签的节点被分组到一个集合中，该集合标识数据库图形中节点的子集，以便于查询。

关系是定向的，每个关系都有一个开始节点和结束节点以及一个关系类型，通过标识具有相同关系类型的相似关系，关系类型起到与节点标签相似的作用。属性可以通过映射模式来指定，映射模式由一个或多个用花括号括起来的“名称:值”对组成。

**示例:**(Lname:“Sharma”，Fname:“Nitin”，Minit:“B”)。

**Neo4j** 图形数据模型类似于传统图论中 *ER 和 EER* 模型中的数据表示方式。

**在 Neo4j 中创建节点:**为**公司创建节点:**T4】

> CREATE (e1: EMPLOYEE，{Empid: '1 '，Lname: 'Sharma '，Fname: 'Nitin '，Minit:' B ' })
> CREATE(E2:EMPLOYEE，{Empid: '2 '，Lname: 'Rao '。Fname:“Rupesh”})
> CREATE(E3:EMPLOYEE，{ Empid:“3”，Lname:“Dave”，Fname:“Gopal”))
> CREATE(E4:EMPLOYEE，{ Empid:“4”，Lname:“Ojha”，Fname:“Baibhav”，Minit:“S”})
> 
> CREATE (d1: DEPARTMENT，{Dno: '1 '，Dname:' Business ' })
> CREATE(D2:DEPARTMENT。{ Dno:“2”，Dname:“Developer”))
> 
> CREATE (p1: PROJECT，{ Pno:“8”，Pname:“WebDeV”})
> CREATE(p2:PROJECt，{ Pno:“2”，Pname:“AppDeV”)
> CREATE(P3:PROJECt，{ Pno:“5”，Pnarne:“ApDeV”})
> 
> CREATE(local 1:LOCATION，{ Name:' Noida ' })
> CREATE(local 2:LOCATION，{ Name:' Hyderabad ' })
> CREATE(local 3:LOCATION，{ Name:' bengalu ' })
> CREATE(local 4:LOCATION，{Name: 'Chennai'})

**在 Neo4j 中创建关系:**为**公司创建关系:**T4】

> CREATE(E1)-[:work for]->(D1)
> CREATE(E3)-[:work for]->(D2)
> 
> CREATE(D1)-[:Manager]->(E2)
> CREATE(D2)-[:Manager]->(E4)
> 
> CREATE(D1)-[:located in]->(loca 1)
> CREATE(D1)-[:located in]->(loca 3)
> CREATE(D1)-[:located in]->(loca 4)
> CREATE(D2)-[:located in]->(loca 2)
> 
> CREATE (e1)- [: WorksOn，{Hours:' 28.5 ' }]->(P1)
> CREATE(E1)-[:WorksOn，{ Hours:' 7.5 ' }]->(p2)
> CREATE(E2)-[:WorksOn，{ Hours:' 15.0 ' }]->(P1)
> CREATE(E2)-[:WorksOn，{ Hours:' 15.0 ' }->(p2)
> CREATE(E2)-[:WorksOn，{ Hours:'

**Neo4j 数据模型特征:**

*   **标签和属性:**创建节点时可以声明/指定节点标签。
    *   也可以创建没有任何标签的节点。
*   **关系和关系类型:****->**指定关系的方向。
    *   这种关系可以在任一方向上遍历。
*   **路径:**路径指定图的一部分的遍历。通常，它用作指定模式的查询的一部分，查询将从图形中检索与该模式匹配的数据。
    *   路径通常由一个开始节点指定，后跟一个或多个关系，通向满足模式的一个或多个结束节点。
*   **可选模式:**图形可以在没有模式的情况下创建和使用(可选)。
    *   与模式创建相关的主要特性包括基于标签和属性创建索引和约束。
*   **索引和节点标识符:***Neo4j*系统在创建节点时为每个节点创建一个内部唯一的系统定义的标识符。为了使用节点的其他属性有效地检索单个节点，用户可以为具有特定标签的节点集合创建索引。