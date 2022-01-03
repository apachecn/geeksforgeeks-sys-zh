# 计算机网络中的 Unicode

> 原文:[https://www.geeksforgeeks.org/unicode-in-computer-network/](https://www.geeksforgeeks.org/unicode-in-computer-network/)

**Unicode** 是提供全面字符集的通用编码系统，由 Unicode 联盟(一组多语言软件制造商)创建。Unicode 简化了软件本地化并改进了多语言文本处理。它克服了 ASCII 和扩展 ASCII 固有的困难。

Unicode 规范了脚本行为，允许从脚本和语言的任意组合中提取的任意字符组合共存于单个文档中。Unicode 定义了其单个字符集的多种编码:UTF-7、UTF-8、UTF-16 和 UTF-32。这些编码之间的数据转换是**无损**。

Unicode 最初是一个 2 字节的字符集。然而，Unicode 第 3 版是一个 **4 字节**代码，完全兼容 ASCII 和扩展 ASCII。

这些都支持对同一组字符进行编码。

*   **UTF-8** 根据字符的不同，每个字符使用 1 到 4 个字节，但是 ASCII 只使用 1 个字节，对于不常见的字符使用 4 个字节。
*   **UTF-16** 大多数字符使用 2 字节，而非常不寻常的字符则需要 4 字节。
*   **UTF-32** 每个字符使用 4 个字节。我们可以通过只计算字节来计算 UTF-32 字符串中的字符数。

该符号使用十六进制数字，格式如下。

**U-XXXXXXXX–**
编号从 **U-00000000 到**U-FFFFFFFF。Unicode 将可用的空间代码分成平面。一个平面是由 65，536 个代码点组成的连续组。最高有效的 16 位定义平面(即平面数= 65，535)，每个平面最多可以定义 65，536 个字符或符号。

**飞机类型–**

1.  **基本多语言平面(BMP)–**平面 0000，基本多语言平面设计为兼容之前的 16 位 Unicode。这个平面中最高有效的 16 位都是零。它主要用不同的语言定义字符集，除了一些控制字符和特殊字符。它被表示为 U+XXXX，其中 XXXX 是最低有效的 16 位，eig。，:U+0900 至 U+09FF 保留给天成文书，孟加拉文 U+2200 至 U+22FF 保留给数学运算等。
2.  **补充多语言平面(SMP)–**平面 0001，补充多语言平面，旨在为 BMP 中排除的多语言字符提供更多代码。例如:10140-1018F 是为古希腊数字保留的。
3.  **补充表意平面(SIP)–**平面 0002，补充表意平面，被设计为提供表意符号的代码，提供与声音相反的思想的符号，例如，20000-2A6DF 被保留给 CJK 统一扩展 B
4.  **补充专机(SSP)–**000E，补充专机，用于特殊字符，如:E0000-E007F 预留标签。
5.  **私人使用飞机(PUPs)–**飞机 000F 和 0010，私人使用飞机为私人使用。字体内部使用它们来引用辅助字形。

**参考–**
[Unicode–msdn . Microsoft](https://msdn.microsoft.com/en-us/library/windows/desktop/dd374081(v=vs.85).aspx)
[数据通信和网络–forouzan](https://www.amazon.in/DATA-COMMUNICATIONS-NETWORKING-Behrouz-Forouzan/dp/0070634149?tag=googinhydr18418-21&tag=googinkenshoo-21&ascsubtag=de868647-8ef7-4c04-95d3-420ac73e7aac)

本文由**喜马拉雅**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。