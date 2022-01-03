# ASCII Vs UNICODE

> 原文:[https://www.geeksforgeeks.org/ascii-vs-unicode/](https://www.geeksforgeeks.org/ascii-vs-unicode/)

**概述:**
Unicode 和 ASCII 是目前全球使用的最流行的字符编码标准。Unicode 是通用字符编码，用于处理、存储和促进任何语言的文本数据交换，而 ASCII 用于表示符号、字母、数字等文本。在电脑里。

[**【ascii】**](https://www.geeksforgeeks.org/ascii-table/)**:**

*   它是电子通信的字符编码标准。美国信息交换标准代码(ASCII)，于 1963 年首次推出。ASCII 码用于在计算机和电信设备中表示文本。
*   ASCII 用于以数字的形式表示 128 个英语字符，每个字母被分配给 0 到 127 范围内的特定数字。例如，大写字母 A 的 ASCII 码是 65，大写字母 B 是 66，依此类推。查看下表了解更多示例。
*   大多数计算机使用 ASCII 编码进行文本表示，这使得从一台设备向另一台设备传输数据变得更加容易。

<figure class="table">

| **描述** | **字符** | **十六进制代码** | **ASCII 值** |
| --- | --- | --- | --- |
| 空间 |   | Twenty | Thirty-two |
| 感叹 | ！ | Twenty-one | Thirty-three |
| 加法符号 | + | 2B | Forty-three |
| 逗号 | , | 2C | forty-four |
| 连字符(减法) | — | 2D | Forty-five |

</figure>

[**Unicode**](https://www.geeksforgeeks.org/unicodedata-unicode-database-python/) **:**

*   Unicode 提供了一种独特的方法，通过为世界上每种口语中的每个字符分配一个唯一的数字来定义它。Unicode 标准由 Unicode 联盟维护，定义了 150 多个现代和历史脚本中的 1，40，000 多个字符以及表情符号。
*   Unicode 可以用不同的字符编码来定义，如 UTF-8、UTF-16、UTF-32 等。其中，UTF 8 是最受欢迎的，因为它在万维网上 90%以上的网站上使用，也在大多数现代操作系统上使用，如视窗系统。

**ASCII Vs Unicode :**
现在我们已经了解了什么是 ASCII 和 Unicode，接下来让我们看看它们之间有什么不同。

**关键因素-1 :**
**规模–**

1.  现在很明显，Unicode 代表的字符比 ASCII 多得多。ASCII 使用 7 位范围来编码仅仅 **128** 个不同的字符。另一方面，Unicode 编码 **154** 书面脚本。我提到表情符号了吗？那些也是。
2.  因此，我们可以说，虽然 Unicode 支持更大范围的字符，但它也比 ASCII 占用更多的空间。

**关键因素-2 :**
**ASCII == UNICODE？**

1.  为了向后兼容，前 128 个 Unicode 字符指向 ASCII 字符。由于 UTF-8 使用 1 字节对这些字符进行编码。
2.  ASCII 本质上只是 UTF-8，或者我们可以说 ASCII 是 Unicode 的一个子集。反之亦然不是真的。

**结论:**
总之，Unicode 和 ASCII 都是文本编码的标准，它们在现代通信中具有最重要的意义。两者都有各自的优缺点，但一个更通用的编码解决方案将始终促进和创造未来通信的便利性。