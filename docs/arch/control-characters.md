# 控制字符

> 原文:[https://www.geeksforgeeks.org/control-characters/](https://www.geeksforgeeks.org/control-characters/)

**控制字符**是不代表可打印字符但用于开始特定动作的字符。控制字符用于执行任何操作，相反，用于在显示器上打印可打印字符。它们还被用作带内信令，除了将符号扩展到内容之外，还会造成其他影响。

另一方面，可打印字符用于在屏幕上显示字符，如字母、符号、数字和字母数字字符。控制字符有不同的种类，包括打印控制字符、数据结构控制字符和传输控制字符。条形码和射频识别扫描仪的前缀或后缀部分经常使用大量这样的字符。

1870 年出现了一种控制字符:NUL 和德尔。1901 年，默里代码包括回车(CR)和换行(LF)，不同的鲍多特代码变体包括其他控制字符。按铃向管理人员发出信号的贝尔字符也是早期的电传操纵字符。

控制字符**分为三部分** 0:

1.  **ASCII control characters –**
    ASCII control character comprises code 0–31 (hex 00–1F). This range is likewise called C0 set. There are two extra controls at 32 and 127 (hex 20 and 7F). ASCII table numbers 0–31 are designated for control characters used to command some peripheral devices, for example, printers. For instance, 12 denotes form feed/new page function. This command instructs printer to go to head of following page.

    这个控制字符集合涵盖了许多应用。有“格式效应器”来管理纯内容的呈现。有用于传输协议的“传输控制”和用于启动、运行和停止辅助设备的“设备控制”。

    有控制不同信息位的“信息分隔符”。存在用于创建警告、显示文件/文本/代码/脚本结尾以及用于处理错误的附加控件。

    ASCII 控制字符包括多种用途，如文本布局、通信和设备控制，这只是冰山一角。

2.  **C1 control characters –**
    C1 covers 128-159 (hex 80-9F). C1 is essentially for displays and printers. This set is identified with ANSI escape sequences and VT100.

    C1 布景于 20 世纪 70 年代末推出。它主要用于控制显示器和打印机小工具，尽管部分控件也有不同的用途。C1 套装是用来搭配 C0 套装的。

    C1 集结合了“格式效应器”，控制打印时的水平和垂直移动。有“表示控件”用于描述换行符或新行的特征。有用于结构和表单填充的“区域定义”控件。

3.  **ISO 8859 特有字符–**
    ISO 8859 是 8 位字符集的集合。这些字符集包括不同的拉丁语、西里尔语、希腊语、阿拉伯语、希伯来语和泰语字符。ISO 8859 被认为是 Windows 字符集(“ANSI 代码页”)，然而它们彼此之间确实是独一无二的。

ISO 8859 有两个重要的特征:不断裂和软连字符。他们中的两个有类似控制角色的属性，尽管事实上他们在 ISO 8859 并不是真正的控制角色。

以下是一些**基本控制代码**:

<center>

| 脱字符符号 | 十六进制代码 | 缩写 | 名字 | 描述 |
| --- | --- | --- | --- | --- |
| @ | 00 | 空 | 空 | 用于执行介质填充和允许间隙。也用于任何代码后的填充和标记字符串的结尾，特别是在编程语言 C/C++中。 |
| A | 01 | 世腾船务 | 标题的开始 | 用作数据广播/消息头的第一个字符。它通常在 Apache Hadoop 中用作字段分隔符。 |
| B | 02 | 酗酒者 | 正文开始 | 标题文本，用于标记标题的结尾。 |
| C | 03 | 电文终了记号(End-of-Text) | 文本结束 | 标记文本的结尾。在键盘输入中，它经常被用作中断字符来中断进程。特别是在基于 Unix 的命令行、nano 编辑器等中。担任(^C)突围指挥。 |
| D | 04 | 磁带结束符 | 传输结束符 | 用于标记一个或多个文本(可能包括标题、广播文本和后文本)的传输结束。在基于 UNIX 的操作系统中，它也用于在终端上标记文件结束。 |
| E | 05 | ENQ | 询问 | 来自远程终端的回复请求，响应可以包括发射机标识和/或发射机状态。 |
| F | 06 | 命令正确应答 | 承认 | 该字符由接收方发送，作为对发送方的批准响应。(对 ENQ 的答复) |
| G | 07 | 命令正确应答 | 铃 | 引起注意的控制字符。它可以控制警报或注意装置。最初，它被用来在终端播放铃声。 |
| H | 08 | 理学士 | 退格键 | 将光标向后移动一个字符位置。在输入模式下，这可能会删除光标左侧的字符。在输出模式下，字符一旦被写入就不能被删除。 |
| 我 | 09 | 高压 | 水平列表 | 将光标移动到同一行中下一个确定的字符位置。 |
| J | 0A | 低频 | 换行 | 将光标移动到下一行的等效字符位置。它用于在 UNIX 中标记行尾。在 DOS/Windows 中，左前用于回车后，表示行尾。 |
| K | 0B | 佛蒙特州 | 纵向制表 | 将光标移到下一行。 |
| L | 0C | 消防 | 换页 | 它命令打印机放弃当前页面并继续打印下一页。更重要的是，它还在各种编程语言中充当空白， |
| M | 0D | 中国国家铁路（China Railway） | 回车 | 最初用于将光标移动到第一列，同时保持在同一行/行。在 DOS，/Windows 中，它在 LF 之前用来标记行尾(EOF)。输入/返回键对应于该字符。 |
| 普通 | 0E | 因此 | 移出 | 切换到替代字符集。 |
| O | 0F | 国际度量单位制 | 移入 | 移出后恢复为常规字符集。 |
| P | Ten | DLE | 数据链接转义 | 它特别用于提供额外的数据传输控制功能。在 DLE 序列中只能使用图形字符和传输控制字符。 |
| Q | Eleven | DC1 | 设备控制 1 (XON) | 一种设备控制字符，主要用于开启或启动基本设备。它也可以用于将任何设备恢复到基本操作模式。 |
| 稀有 | Twelve | DC2 | 设备控制 2 | 一种设备控制字符，基本上专用于开启或启动基本设备。它也可以用于将任何设备设置为特殊操作模式 |
| S | Thirteen | DC3 | 设备控制 3 (XOFF) | 一种基本上专用于关闭或停止一个重要设备的设备控制字符。也用作第二步停止(例如:等待、暂停、待机或暂停) |
| T | Fourteen | DC4 | 设备控制 4 | 一种设备控制字符，主要用于关闭所有设备。它也可以用于其他 DCs 不允许的任何设备控制目的。 |
| U | Fifteen | (电传等的)否定应答(negative acknowledge) | 否定应答 | 由接收机发送给发射机的一种控制字符，作为否定确认/响应。NAK 还指示在最后接收的块中识别出错误。 |
| V | Sixteen | synchronizing 同步 | 同步空闲 | 由同步传输网络用来提供信号，从该信号可以在数据终端设备之间实现同步整流 |
| W | Seventeen | 信息组传送结束(End of Transmission Block) | 字组传送结束字符 | 标记数据传输段的结束(其中数据被分成这样的段用于传输) |
| X | Eighteen | 能 | 取消 | 指示它前面的数据有错误。因此，数据将被忽略。 |
| Y | Nineteen | 东地中海(Eastern Mediterranean) | 媒体结尾 | 一种控制字符，可用于查找介质的物理结尾或数据所需部分的结尾。 |
| Z | 1A | 潜水艇 | 代替者 | 用作已被检测为无效或错误的字符的替代。在 Unix 上，^Z 是暂停进程的键盘信号。在 DOS/Windows 中，用于标记文件的结尾，在 cmd 终端中，用于标记文本文件和许多脚本。 |
| [ | 1B | 经济社会委员会 | 逃跑 | Esc 键在几乎所有的操作系统中都对应这个控制字符。用于许多界面，以逃避屏幕，菜单或进程。, |
| \ | 1C | 空军上士 | 文件分隔符 | 用于逻辑分离数据，必须为每个应用程序定义其特定用途。当以层次顺序使用时，它划分称为文件的数据项。 |
| ] | 1D | (美国联邦政府职员)总表(General Schedule) | 分组分隔符 | 用于逻辑分离数据；必须为每个应用程序定义其特定目的。当以层次顺序使用时，它划分称为组的数据项。 |
| ^^ | 1E | 标准英语 | 记录分离器 | 用于逻辑分离数据；必须为每个应用程序定义其特定目的。当以层次顺序使用时，它划分称为记录的数据项。 |
| ^_ | 1F | 美国 | 单元分隔符 | 用于逻辑分离数据；必须为每个应用程序定义其特定目的。当以层次顺序使用时，它划分称为单位的数据项。 |
|  | Twenty | 特殊卡 | 空间 | 空间是图形特征。将光标移动一个字符位置。 |
| ？ | 7F | 是吗 | 删除 | 删除控制字符是 ASCII 曲目中的最后一个字符。它旨在删除不正确的字符。 |

</center>