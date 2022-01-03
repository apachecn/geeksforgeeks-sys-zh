# 啦啦队员和木偶师的区别

> 原文:[https://www . geeksforgeeks . org/cheerio-and-puppeter 的区别/](https://www.geeksforgeeks.org/difference-between-cheerio-and-puppeteer/)

**1。**[**Cheerio**](https://www.geeksforgeeks.org/nodejs-web-crawling-using-cheerio/)**:**
正是 nodejs Module 的实现基于核心 jquery。它与一个非常简单和一致的 DOM 模型一起工作。Cheerio 广泛用于网页抓取工作，有时也用于任务自动化。它基于 jquery，速度非常快。Cheerio 包装了 Parse5 解析器，能够解析任何类型的 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 和 [XML](https://www.geeksforgeeks.org/xml-basics/) 文档。

**2。** [**木偶师**](https://www.geeksforgeeks.org/node-js-puppeteer/) **:**
木偶师广泛用于自动化浏览器任务，只能与谷歌 chrome 无头浏览器即 chrome 配合使用。木偶师也可以用于网页抓取任务，但另一方面，它功能强大，充满了 cheerio 模块中没有的许多功能

**切里欧和木偶师的区别:**

<figure class="table">

| 没有。 | 再见 | 操纵木偶的人 |
| --- | --- | --- |
| 1. | 它由 CheerioJS 开发和维护。 | 它由谷歌开发和维护。 |
| 2. | 它不能解析 Javascript。 | 它能够解析 Javascript。 |
| 3. | 用 react 或 angular 构建的网站不能用这个刮擦。 | 用 react 或 angular 构建的网站可以用这个刮擦。 |
| 4. | 它不提供截图和制作 pdf 等功能。 | 你可以用木偶师截图并保存 pdf。 |
| 5. | 与木偶师相比，它更快。 | 它比 cheeriojs 慢。 |
| 6. | Cheerio 只是一个解析 HTML 和 XML 的 DOM 解析器。 | 而木偶师带来了整个浏览器引擎。 |
| 7. | Cheerio 非常适合刮擦任务。 | 木偶师主要用于浏览器自动化。 |
| 8. | Cheerio 可以和 chrome 一起工作。 | 木偶师需要铬来运行脚本。默认情况下，铬是无头的。 |
| 9. | Cheerio 只能处理原始的 HTML 数据。 | 它支持原始的 HTML、XML，并且能够执行 JavaScript。 |

</figure>