# Neo4j |命名规则和建议

> 原文:[https://www . geesforgeks . org/neo4j-命名规则和建议/](https://www.geeksforgeeks.org/neo4j-naming-rules-and-recommendations/)

几乎没有命名规则，节点标签、关系类型、属性名称和变量的命名必须遵循一些规则，除非出现错误。

**命名规则:**

*   To name node labels, relationship types, attribute names and variable names, you should start with a letter. This may also be a non-English character. If you need numeric characters to name anything mentioned above, you can use **and** to escape non-letter characters like **` n`** .
*   Names that can contain numbers but cannot be placed in the first place like **1 geeks** are not allowed. You can use it as **geek 1** or **geek 1** . However, if you have to add a number at the beginning, you can also use **to reverse the hook** , just like **and "1 geek"** , the reverse hook will skip 1, and other characters will behave as it should.
*   The naming in Secondary cannot contain any special naming symbol. However, underlining is allowed. If special symbols are needed, use **to check** .
*   The name can be 65535 (2 16-1) or 65534, which basically depends on the version of Secondary.
*   The naming in Secondary is case-sensitive, just like **: geeks** , **: geeks** and **: geeks** are three different labels, and **g** and **g** are different variables.
*   White space characters are acceptable, and all leading and trailing white space characters will be automatically deleted. Like *match (a) return* a is equivalent to *match (a) return a* . If a space is needed in the name, use **and** to escape, such as **"My variable has a space"** .

**范围和名称空间规则:**

*   All node labels, relationship types and attribute names can reuse names. The following inquiries? —? Label, type and attribute name are used? —? Valid:

    ```
    CREATE (a:a {a: 'a'})-[r:a]?(b:a {a: 'a'}).
    ```

*   Variables of node and relationship must not have duplicate names in the same query range. The following query is invalid because both nodes and relationships have the name

    ```
    a: CREATE (a)-[a]?(b)
    ```

**推荐用于命名节点标签、关系类型、属性名称和变量:**

*   **Node label:** Try to use Camel case, starting with uppercase characters, as shown in the following example.

    ```
    :GeeksforGeeks rather than :geeksforgeeks
    ```

*   **Relationship type:** Try to use capital letters, and use underscores to separate words

    ```
    :Geeks_for_Geeks rather than :geeksForGeeks 
    ```

***参考:***[https://neo4j.com/docs/cypher-manual/current/syntax/naming/](https://neo4j.com/docs/cypher-manual/current/syntax/naming/)