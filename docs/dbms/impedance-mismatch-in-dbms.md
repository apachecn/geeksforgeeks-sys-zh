# 数据库管理系统中的阻抗不匹配

> 原文:[https://www.geeksforgeeks.org/impedance-mismatch-in-dbms/](https://www.geeksforgeeks.org/impedance-mismatch-in-dbms/)

阻抗不匹配是指由于数据库模型和编程语言模型之间的差异而出现的问题。实用的关系模型有 3 个组件，它们是:

1.  属性及其数据类型
2.  元组
3.  桌子

**问题:**
由于阻抗不匹配，可能会出现以下问题:

1.  可能出现的第一个问题是，数据类型不匹配意味着编程语言属性数据类型可能不同于数据模型中的属性数据类型。

    因此，为每种宿主编程语言建立一个绑定是非常必要的，该绑定为每种属性类型指定兼容的编程语言类型。需要有不同的数据类型，比如我们有不同编程语言可用的不同数据类型，比如 C 语言中的数据类型不同于 Java，两者都不同于 SQL 数据类型。
2.  The second problem that may occur is because the results of most queries are sets or multisets of tuples and each tuple is formed of a sequence of attribute values. In the program, it is necessary to access the individual data values within individual tuples for printing or processing.

    Hence there is a need for binding to map the query result data structure which is a table to an appropriate data structure in the programming language. A mechanism is needed to loop over the tuples in a query result in order to access a single tuple at a time and to extract individual values from the tuple.
    The extracted values are typically copied to appropriate program variables for further processing by the program.

    游标或迭代器是一个变量，用于循环查询结果中的元组。每个元组中的单个值被提取到适当数据类型的不同或唯一程序变量中。

当设计一种特殊的数据库编程语言，使用与数据库模型相同的数据模型和数据类型时，例如 Oracles 的 sPL/SQL，阻抗不匹配就不是问题。

**示例–**[UGC NET CS 2016 年 8 月–三|问题 7](https://www.geeksforgeeks.org/ugc-net-ugc-net-cs-2016-aug-iii-question-7/)