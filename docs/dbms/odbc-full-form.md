# ODBC 完整表单

> 原文:[https://www.geeksforgeeks.org/odbc-full-form/](https://www.geeksforgeeks.org/odbc-full-form/)

ODBC 代表**开放数据库连接**。

它是一个开放标准[应用程序编程接口](https://www.geeksforgeeks.org/introduction-to-apis/)也称为 API，用于访问数据库。第一个 ODBC 驱动程序是在 1992 年建立的，当时微软与辛巴合作，命名为 Simba。借助程序中的 ODBC 语句。我们可以访问许多不同或公共数据库中的不同文件。

**历史:**
第一个 ODBC 标准是微软在 1992 年推出的。这个驱动程序是一个标准模型，基本上是为了统一访问不同的 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 数据库而设计的。看到 ODBC 的巨大成功，微软引入了另一个名为 OLE DB 的数据库，它将是比 ODBC 更广泛的数据访问标准。它基本上是一种数据访问标准，可以在 SQL 数据库之外执行，并扩展到可以以行和列的形式表示数据的不同类型的数据源。

微软的基本计划是 OLE DB 将取代 ODBC 成为最常见的数据访问标准。最近，微软推出了另一个名为 ADO 的数据访问标准。ADO 应该比 OLE DB 工作得更远，因为 ADO 更面向对象。

随着如此多的进步，减少使用 ODBC 并没有成功，因为 ODBC 仍然是 SQL 数据源事实上的数据访问标准。背后的主要原因是其跨平台数据访问标准的强大。如今，不同 SQL 数据源最常见的数据访问标准仍然是 ODBC 和 JDBC，而不是 OLE DB 或 ADO。

**ODBC 的组件:**
ODBC 主要有 4 个组件，如下:

1.  **应用–**
    这个组件基本上是调用 ODBC 函数，提交 SQL 语句。

2.  **驱动程序管理器–**
    该组件的作用是为每个应用程序加载驱动程序。

3.  **驱动程序–**
    该组件的角色是处理所有函数调用，然后将每个 SQL 请求提交给数据源。

4.  **数据源–**
    该组件访问数据的作用。

**ODBC 的特点:**
以下是 ODBC 的一些特点:

*   **Error Codes –** 
    ODBC basically supports error code mechanism to show issues which caused error to occur while processing SQL statements. 
*   **Attributes –** 
    Beside Error Code feature it also provides different types of functions to get details of attributes and functions that are used in drivers. 
*   **Rich metadata –** 
    ODBC also provides huge support to data about data also known as metadata. ODBC also provides different functions to get data about both functions and data types used. 
*   **Inter-operability –** 
    The most important feature of ODBC is its interoperability that means using ODBC driver we can develop different applications that can communicate with different DB also known as Database Management System and switching our application from one database to another will not create any problem. 
*   **SQL 语法–**
    ODBC 基本上实现了 SQL 语法，便于用户理解，因为 SQL 语法很容易被最终用户理解。每当用户将一条 SQL 语句传递给 ODBC 驱动程序时，它都会将给定的语句与 SQL 92 标准相匹配，并将其转换为底层数据库接受的相应 SQL 语句。
    1.  它很好地集成到许多不同的 RAD 工具中。

    2.  在不同的开发环境中，如 Powerbuilder、Delphi、Visual Basic 和 Java 等，它可以轻松地与各种“数据绑定”组件接口。

    3.  它基本上简化并加快了应用程序开发。

    4.  借助于 ODBC 提供的模板，它还有助于一次编辑多个不同的对象。

    5.  它还允许最大的互操作性，这基本上意味着单个应用程序可以轻松访问不同的数据库管理系统，或者我们也可以说，基于用户需求或可用的数据库管理系统类型，ODBC 允许单个应用程序处理不同类型的数据库管理系统。

    6.  借助内置功能，我们可以创建自定义应用程序。

**ODBC 的缺点:**

尽管 ODBC 有很多优点和特点，但也有一些缺点，如下所示:

1.  **大型数据库速度慢–**
    随着数据库规模的增加，ODBC 的速度降低。

2.  **服务器不标准化–**
    在 ODBC 中，由于大部分工作是由客户端或用户完成的，所以很难扩展，而且这些 ODBC 驱动程序也不标准化。因为哪些客户端维护自己的驱动程序，命名表给大型站点的管理带来了问题。

3.  **构建复杂–**
    这些 ODBC 驱动程序构建复杂，维护也复杂。

4.  **依赖于框架–**
    由于 ODBC 规范只指定了应用协议，所以它基本继承了使用它的框架的特性。因此，我们可以说可靠性取决于正在使用的底层框架的请求/响应协议的实现。