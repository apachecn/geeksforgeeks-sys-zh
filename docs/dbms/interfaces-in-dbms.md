# 数据库管理系统中的接口

> 原文:[https://www.geeksforgeeks.org/interfaces-in-dbms/](https://www.geeksforgeeks.org/interfaces-in-dbms/)

数据库管理系统(DBMS)界面是一种用户界面，允许在不使用查询语言本身的情况下向数据库输入查询。

数据库管理系统提供的用户友好界面可能包括以下内容:

1.  **基于菜单的网络客户端或浏览界面–**
    这些界面向用户呈现选项列表(称为菜单)，引导用户形成请求。使用菜单的基本优点是，它们消除了记住任何查询语言的特定命令和语法的紧张感，而不是查询基本上是通过从系统基本上显示的菜单中收集或挑选选项来逐步组成的。下拉菜单在*基于网络的界面*中是一种非常流行的技术。它们也经常用于*浏览界面*，允许用户以探索和非结构化的方式浏览数据库的内容。
2.  **基于表单的界面–**
    基于表单的界面向每个用户显示一个表单。用户可以填写所有表单条目以插入新数据，也可以只填写某些条目，在这种情况下，数据库管理系统将为其他剩余条目兑换相同类型的数据。这种类型的表单通常是为没有操作系统专业知识的用户设计、创建和编程的。许多数据库管理系统都有*表单规范语言*，这是帮助指定此类表单的特殊语言。
    示例:SQL* Forms 是一种基于表单的语言，它使用结合关系数据库模式设计的表单来指定查询

*   **图形用户界面–**
    图形用户界面通常以图表形式向用户显示模式。然后，用户可以通过操作图表来指定查询。在许多情况下，图形用户界面利用菜单和表单。大多数图形用户界面使用鼠标等定点设备来选择显示的模式图的特定部分。*   **Natural language Interfaces –**
    These interfaces accept request written in English or some other language and attempt to understand them. A Natural language interface has its own schema, which is similar to the database conceptual schema as well as a dictionary of important words.

    自然语言接口引用其模式中的单词以及字典中的一组标准单词来解释请求。如果解释成功，接口将生成一个对应于自然语言的高级查询，并将其提交给数据库管理系统进行处理，否则将与用户开始对话，以澄清任何提供的条件或请求。这样做的主要缺点是，这种类型的接口的功能没有那么先进。

    *   **Speech Input and Output –**
    There is an limited use of speech say it for a query or an answer to a question or being a result of a request it is becoming commonplace Applications with limited vocabularies such as inquiries for telephone directory, flight arrival/departure, and bank account information are allowed speech for input and output to enable ordinary folks to access this information.

    使用预定义的单词检测语音输入，并用于设置提供给查询的参数。对于输出，发生了从文本或数字到语音的类似转换。

    *   **数据库管理员界面–**
    大多数数据库系统都包含特权命令，只能由数据库管理员使用。这些命令包括创建帐户、设置系统参数、授予帐户授权、更改模式、重新组织数据库的存储结构。