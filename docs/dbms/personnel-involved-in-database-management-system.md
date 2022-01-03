# 数据库管理系统涉及人员

> 原文:[https://www . geeksforgeeks . org/人员-数据库参与-管理-系统/](https://www.geeksforgeeks.org/personnel-involved-in-database-management-system/)

许多人参与设计、使用和维护一个有几百个用户的大型数据库。在这里，我们将考虑那些可能被称为“现场演员”的人，他们的工作涉及大型数据库的日常使用。

1.  **Database Administrators:**
    Administrating the primary (database) and secondary (DBMS and related software) is the responsibility of the *database administrator (DBA)*. The DBA is responsible for authorizing access to the database, for coordinating and monitoring its use, and for acquiring software and hardware resources as needed.
2.  **数据库设计者:**
    数据库设计者负责识别要存储在数据库中的数据，并选择合适的结构来表示和存储这些数据。数据库设计人员通常会与每个潜在的小组和用户进行交互，并开发一个符合这些小组的数据和处理要求的数据库的*视图*。

*   **[End Users](https://www.geeksforgeeks.org/categories-of-end-users-in-dbms/):**
    End users are the people whose jobs require access to the database for querying, updating and generating reports; the database primarily exists for their use.

    有几类最终用户:

    *   **临时最终用户:**
        偶尔会访问数据库，但每次可能需要不同的信息。他们通常是中级或高级经理或其他偶尔的浏览器。
    *   **天真或参数化最终用户:**
        他们的主要工作功能围绕着不断查询和更新数据库，使用经过精心编程和测试的标准类型的查询和更新。银行出纳员、航空公司、酒店等的预订员就是天真终端用户的例子。
    *   **复杂的最终用户:**
        复杂的最终用户包括工程师、科学家、业务分析师和其他完全熟悉数据库管理系统设施的人，以便实施他们的应用程序来满足他们复杂的需求。
    *   **独立用户:**
        他们通过使用现成的程序包来维护个人数据库，这些程序包提供了易于使用的菜单或基于图形的界面。*   **软件工程师:**
    系统分析师确定最终用户的需求，尤其是幼稚和参数化的最终用户，并为满足这些需求的固定交易制定规范。*应用程序员*将这些规范作为程序实现；然后他们测试、调试、记录和维护这些固定的事务。这样的分析师和程序员被称为*软件工程师*。