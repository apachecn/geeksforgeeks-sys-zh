# 恢复删除的数字证据

> 原文:[https://www . geesforgeks . org/recovery-deleted-digital-evidence/](https://www.geeksforgeeks.org/recovering-deleted-digital-evidence/)

根据一项调查，93%的信息从未离开过数字形式。如今，大多数信息都是完全以数字形式创建、修改和消费的。这意味着大多数电子表格和数据库永远不会在纸上制作，大多数数字快照永远不会打印出来。在本文中，我们将讨论恢复删除的数字证据的方法和技术。

### 什么是数字证据？

数字证据是以数字形式存储或传输的任何信息，法庭上的一方可以在审判时使用。数字证据可以是音频文件和语音记录、地址簿和联系人列表、各种程序的备份，包括移动设备的备份、浏览器历史记录、Cookies、数据库、压缩存档(ZIP、RAR 等)。)包括加密档案等。

### 销毁的证据

在刑事或网络犯罪案件中，销毁证据的企图非常普遍。这种尝试或多或少会成功，取决于以下条件:

*   采取行动销毁证据。
*   销毁证据的可用时间。
*   存储设备类型，如磁性硬盘、闪存卡或固态硬盘。

在这一节中，我们将讨论销毁证据的一些**方法**和收回被销毁证据的**方法**。

## 删除的文件

删除文件是销毁证据最简单、最方便、最重要的方法之一。无论是使用“删除”按钮还是“Ctrl+Delete”按钮。已删除文件的文件恢复原则是基于这样一个事实，即当文件被删除时，Windows 不会擦除其内容。相反，存储已删除文件在磁盘上的确切位置的文件系统记录将被标记为“已删除”，已删除文件先前占用的磁盘空间将被标记为可用，但不会被零或其他数据覆盖。

*   删除的文件可以通过分析回收站的内容来检索，因为它们在被删除之前会暂时存储在回收站中。
*   如果删除的文件在回收站中没有痕迹，如“Ctrl+Delete”命令的情况，那么，在这种情况下，您可以使用商业恢复工具来恢复删除的证据。商业工具的一个例子是[磁盘内部分区恢复](https://www.diskinternals.com/)。
*   通过分析文件系统和/或扫描整个硬盘来查找已知文件类型的特征签名，可以成功恢复:
    *   用户删除的文件。
    *   办公室文件的临时副本(包括这些文件的旧版本和修订版)。
    *   许多应用程序保存的临时文件。
    *   重命名的文件。
*   存储在已删除文件中的信息可以用从其他来源收集的数据来补充。例如，Skype 中的“chatsync”文件夹存储了内部数据，这些数据可能包含大量用户对话。这意味着，如果“chatsync”文件夹存在，即使删除了 Skype 数据库，也有可能恢复用户聊天。许多工具都是为了这个目的而存在的，比如[贝尔卡索证据中心 2020](https://belkasoft.com/ec) 。

## 格式化硬盘

从格式化硬盘恢复数据取决于许多参数。格式化硬盘中的信息可以使用数据雕刻技术或商业数据恢复工具进行恢复。
硬盘格式化有两种可能的方式:**全格式化和**快速格式化。

**完全格式化–**顾名思义，这将通过在正在格式化的分区上创建新的文件系统来初始化磁盘，并检查磁盘是否有坏扇区。在 Windows Vista 之前，完全格式化操作不会将正在格式化的磁盘清零。取而代之的是，Windows 会一个扇区接一个扇区地扫描磁盘表面。不可靠的部门将被标记为“坏”。但是在 Vista 和 Windows 7 的情况下，全格式操作实际上会:

*   将磁盘擦干净。
*   将零写入磁盘。
*   回读扇区以确保可靠性。

**快速格式化–**除了固态硬盘的情况外，这从来都不是破坏性的。磁盘格式只是通过在正在格式化的分区上创建新的文件系统来初始化磁盘。使用快速格式化方法清除的磁盘中的信息可以通过使用支持数据雕刻的数据恢复工具之一来恢复。

## 固态硬盘

固态硬盘意味着固态硬盘代表了一种新的存储技术。

*   它们的运行速度比传统驱动器快得多。
*   他们采用完全不同的方式在内部存储信息，这使得销毁信息变得容易得多，恢复信息变得困难得多。

SSD 中的罪魁祸首是 **TRIM 命令**。根据一项调查，TRIM 使 SSD 能够在不到 3 分钟的时间内完全擦除所有删除的信息。这意味着一旦被操作系统标记为删除，TRIM 命令就有效地将所有信息归零。此外，即使使用写阻止设备也无法防止 TRIM 命令的影响。

当我们试图从固态硬盘中恢复已删除的数据，甚至从以完整格式或快速格式格式化的固态硬盘中恢复任何信息时，传统方法没有用。这意味着只有在没有发出 TRIM 命令或至少有一个组件不支持 TRIM 时，传统方法才能用于 SSD 中的数据恢复。这些组件包括:

*   **操作系统版本:** Windows Vista 和 Windows 7 支持 TRIM 命令，另一方面，Windows XP 及更早版本一般不支持 TRIM 命令。
*   **通信接口:** SATA 和 eSATA 支持 TRIM，而通过 USB、LAN 或 FireWire 连接的外部机箱则不支持。
*   **文件系统:** Windows 支持 NTFS 卷上的 TRIM，但不支持 FAT 格式的磁盘上的 TRIM。另一方面，Linux 支持所有类型的卷上的 TRIM，包括那些用 FAT 格式化的卷。

## 数据雕刻

雕刻意味着对硬盘的全部内容进行精确的逐位检查。数据雕刻的概念与文件恢复完全不同。雕刻允许:

*   识别特定的签名或模式，这些签名或模式可能会提示一些有趣的数据可以存储在磁盘上的特定位置。
*   定位各种否则无法获得的工件。

寻找被销毁的证据时，数据雕刻真的很神奇。在数据雕刻的情况下，调查人员不需要依赖文件，因为它们可能会被部分覆盖、碎片化并散落在磁盘上。当我们处理文本内容时，数据雕刻具有以下特征:

*   文本信息最容易恢复。
*   包含文本数据的块只填充属于代表字母、数字和符号的浅范围的数值。
*   当雕刻文本数据时，调查人员必须考虑各种语言和文本编码。例如，土耳其字符集不同于拉丁语，也与阿拉伯文、中文或韩文没有任何共同之处。
*   在查找每种支持语言的文本时，必须考虑不同的编码。
*   通过分析从磁盘上读取的特定语言和特定编码的信息，通常可以检测到文本信息。

在二进制数据的情况下:

*   二进制数据非常随机。
*   通过计算不属于给定语言/编码组合的字符数，很容易检测出每个文本块的开头和结尾。
*   一旦达到设定的阈值，就认为算法已经到达给定文本块的末尾。

**数据雕刻的局限性–**

*   不是所有格式的数据都可以被雕刻。
*   数据雕刻是基于寻找特征签名或模式。例如，JPEG 文件通常在开头有“JFIF”签名，后面是文件头。ZIP 存档以“PK”开头，PDF 文件以“%PDF”开头。
*   有些文件可能是一个真正的二进制文件，在其头部没有任何永久签名。比如 QQ 信使。
*   在大多数情况下，基于文本的文件可能是一个问题，因为有大量的纯文本文件可以存储在电脑上。
*   在使用特殊算法用加密性强的随机数据来填充以前被敏感信息占据的磁盘空间的情况下，不能使用数据雕刻。
*   在“偏执”模式下，敏感信息会被多次覆盖，甚至无法进行最佳和洁净室类型的提取。
*   如果敏感信息没有存储在硬盘上，而是存储在内存中。在这种情况下，数据雕刻是不可能的。这里唯一可行的选择是“实时内存分析”。
*   数据雕刻在固态硬盘中相当无用和不可能。