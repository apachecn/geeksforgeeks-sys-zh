# 硒远程网络驱动和硒网络驱动的区别

> 原文:[https://www . geesforgeks . org/selenium-remote-web driver-and-selenium-web driver/](https://www.geeksforgeeks.org/difference-between-selenium-remote-webdriver-and-selenium-webdriver/)的区别

**1。硒远程网络驱动程序:**
它是一个用于在分布式环境或远程计算设备上执行浏览器自动化和执行评估的界面。换句话说，它是一个实现网络驱动程序接口的类，这个动作是在远程服务器上执行的。一个浏览器有不同的驱动类，比如 ChromeDriver、FirefoxDriver 等。

**2。[Selenium Webdriver](https://www.geeksforgeeks.org/components-of-selenium/):**
它通过一些自动化脚本帮助你直接与浏览器交互，这些脚本包括一个起点，各种变量及其绑定值，以及源代码。它用来给各种平台提供支持，它的执行速度比 Selenium IDE 或 RC 快不了多少。它提供了多个客户端库，可以使用不同的编程语言，如 [Python](https://www.geeksforgeeks.org/python-programming-language/) 、 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [Java](https://www.geeksforgeeks.org/java/) 等。用于为硒测试建立自动化。

**硒远程网络驱动和硒网络驱动的区别:**

<center>

| 没有。 | 硒远程网络驱动程序 | 硒网络驱动程序 |
| --- | --- | --- |
| 1. | 这是一个实现网络驱动程序接口的类。 | 这是一个接口，要使用它，需要 org.openqa.selenium.*包。 |
| 2. | 它有一些额外的方法用于实现类。 | 与用于接口实现的远程网络驱动程序相比，它的方法较少。 |
| 3. | 在这种情况下，对象用于管理网格中的浏览器。 | 在这种情况下，许多浏览器由 Webdriver 对象管理。 |
| 4. | 远程网络驱动程序是网络驱动程序的一部分。 | 它不是任何网络驱动程序的一部分。 |
| 5. | 它提供了像 startSession()、getSessionId()等方法。 | 它提供了类似 quit()、get()等方法。 |
| 6. | 要测试这一点，需要远程机器。 | 它可以在本地机器上测试。 |
| 7. | 它不依赖于操作系统。 | 这取决于操作系统。 |

</center>