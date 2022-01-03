# POM 和页面工厂的区别

> 原文:[https://www . geeksforgeeks . org/POM 和 pagefactory 之间的差异/](https://www.geeksforgeeks.org/difference-between-pom-and-pagefactory/)

**1。[页面对象模型(POM)](https://www.geeksforgeeks.org/page-object-model-pom/) :**
页面的对象是一个 OOPs 类，作为被测应用程序网页的接口，它实际上是一种设计模式，通常在 Selenium for Automation Test Cases 中使用。这个 POM 中的页面类结合了网络因素和与网络元素互动的技术。

**2。页面工厂:**
硒网络驱动程序提供了一个名为页面工厂的类，帮助设计模式的页面对象。在这种情况下，开发人员使用注释“@FindBy”。有一种叫做“initElements”的方法，用于初始化网站的元素。

**POM 和 PageFactory 的区别:**

<center>

| 没有。 | 砰的一声 | 页面工厂 |
| --- | --- | --- |
| 1. | 这是一种设计模式的方法。 | 这是一个由 Selenium Webdriver 提供的类。 |
| 2. | 这不是处理任务的最佳方法。 | 这是处理任务的最佳方法。 |
| 3. | 它有助于分离页面对象和脚本。 | 这是一种实现 POM 的技术。 |
| 4. | “By”注释用于定义页面对象。 | 它使用注释“查找比”来描述页面对象。 |
| 5. | 它不能有效地处理异常。 | 它有效地处理异常。 |
| 6. | 它需要初始化每个对象。 | 它不需要初始化每个对象。 |
| 7. | 有用于执行任务的缓存存储。 | 不需要缓存存储。 |

</center>