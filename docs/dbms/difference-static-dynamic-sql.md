# 静态和动态 SQL 的区别

> 原文:[https://www . geesforgeks . org/difference-static-dynamic-SQL/](https://www.geeksforgeeks.org/difference-static-dynamic-sql/)

**静态或嵌入式** SQL 是应用程序中的 SQL 语句，在运行时不会改变，因此可以硬编码到应用程序中。**动态** SQL 是运行时构造的 SQL 语句；例如，应用程序可以允许用户输入他们自己的查询。

**动态** SQL 是一种编程技术，使您能够在运行时动态构建 SQL 语句。您可以通过使用动态 SQL 创建更通用、更灵活的应用程序，因为 SQL 语句的全文在编译时可能是未知的。

使用静态 SQL 有一个好处，那就是优化了语句，从而使应用程序具有高性能，因为它提供了比动态 SQL 更好的灵活性，并且由于动态语句的访问计划是在运行时生成的，所以它们必须在应用程序中准备好，这是您在静态 SQL 中永远不会看到的，但这不是它们之间的唯一区别， 因此我们可以说，动态 SQL 相对于静态语句只有一个优势，一旦应用程序被编辑或升级，静态语句就可以被清楚地注意到，所以有了动态语句，就不需要预编译或重新构建，只要访问计划是在运行时生成的，而静态语句需要在访问计划被修改时重新生成，除了动态 SQL 需要更多权限的事实之外，它也可能是执行未授权代码的一种方式， 我们不知道我们会有什么样的用户，所以为了安全起见，如果程序员没有处理好的话，它可能是**危险的**。

下面提到的是**静态** *或* **嵌入式**和**动态** *或* **交互** SQL 的基本区别:

| 静态(嵌入式)SQL | 动态(交互式)SQL |
| 在静态 SQL 中，如何访问数据库是在嵌入式 SQL 语句中预先确定的。 | 在动态 SQL 中，如何访问数据库由运行时决定。 |
| 更加快捷高效。 | 它不那么迅速和有效。 |
| SQL 语句在编译时编译。 | SQL 语句在运行时编译。 |
| 应用程序计划的解析、验证、优化和生成是在编译时完成的。 | 应用程序计划的解析、验证、优化和生成是在运行时完成的。 |
| 它通常用于数据均匀分布的情况。 | 它通常用于数据分布不均匀的情况。 |
| 不使用 EXECUTE IMMEDIATE、EXECUTE 和 PRECute 语句。 | 使用了 EXECUTE IMMEDIATE、EXECUTE 和 PRECute 语句。 |
| 它不太灵活。 | 它更灵活。 |

**动态 SQL 的限制:**
我们不能动态使用某些 SQL 语句。
与静态 SQL 相比，这些语句的性能较差。

**静态 SQL 的局限性:**
它们在运行时不会改变，因此被硬编码到应用程序中。