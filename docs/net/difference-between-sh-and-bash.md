# sh 和 bash 的区别

> 原文:[https://www . geesforgeks . org/sh 和-bash 的区别/](https://www.geeksforgeeks.org/difference-between-sh-and-bash/)

bash 和 sh 是 Unix 操作系统的两种不同外壳。bash 是 sh，但是有更多的特性和更好的语法。Bash 是“Bourne shell”，是对 sh(原 Bourne shell)的改进。Shell 脚本是任何 shell 中的脚本，而 Bash 脚本是专门为 Bash 编写的脚本。sh 是 Unix/类 Unix 操作系统的 shell 命令行解释器。sh 提供了一些内置命令。bash 是 sh 的超集。Shell 是一个命令行界面，用于运行命令和 shell 脚本。外壳有多种风格，就像操作系统有多种风格一样。所以，Shell 是用户和操作系统之间的接口，帮助用户与设备进行交互。

## sh:

```
#!/bin/sh
```

## bash:

```
#!/bin/bash
```

### 注意:

*   Shell 是用户和操作系统之间的接口。
*   sh 实现了外壳接口。
*   bash 是 sh 的超集。

## sh:

sh 也叫伯恩·谢尔。sh 是 POSIX 标准描述的命令编程语言。它适用于 UNIX 或类似 UNIX 的操作系统。它有许多实现。在大多数操作系统上，sh 是由 dash、kash 和原始的 Bourne Shell 等程序实现的。sh 是 bash 的前身。/bin/sh 是主要实现的实际链接。它是大多数 POSIX 系统中的符号链接。

sh 本身并不是一种编程语言。它只是一个规范。sh 是对语言语法和语义的详细描述。它不包括实现。sh 是作为早期 UNIX 外壳的替代品而编写的。它的大部分语法与 ALGOL68 编程语言的语法相同。

如果我们想让我们的语言兼容多个系统，我们应该使用 sh。sh 脚本最喜欢在 bash 上运行，也无需修改，因为 bash 与 sh 向后兼容。sh 是在大多数 POSIX/Unix/Linux 系统上工作的最具可移植性的脚本语言。sh 的一个优点是它保证存在于任何声称是 Unix 系统的东西上。

## bash:

bash 也是一种类似 sh 的命令编程语言。如今，bash 是大多数基于 Linux 的操作系统上的默认登录外壳。它是 sh 系统的扩展版本，用于代替伯恩外壳的 GNU。我们也可以说 bash 是一种编程语言。这里像 python 一样思考，我们可以在交互模式下启动 python，它的行为就像一个 shell，但是我们也可以在任何 IDE 上运行 python 程序。

bash 是 sh 的超集。这意味着 bash 支持 sh 的特性，并提供比 sh 更多的功能。虽然大多数命令都和 sh 做同样的事情。bash 不是一个符合 POSIX 的外壳。它是 POSIX 外壳语言的一种方言。Bash 可以在文本窗口中运行，并允许用户解释命令来完成各种任务。它具有 Korn 和 C 外壳最好和最有用的特性，例如目录操作、作业控制、别名和许多其他特性。

像 GNU 软件 bash 提供的其他外壳一样，包括 csh 的一个版本，Bash 是默认的外壳。bash 旨在成为 IEEE POSIX 规范(IEEE 标准 1003.1)的 IEEE POSIX 外壳和工具部分的一致实现。和其他 GNU 一样，bash 也是相当便携的。这适用于任何基于 Linux/Unix 的系统，只要该系统在预期位置有 bash。就编程和交互使用而言，bash 比 sh 功能更强。

### sh 和 bash 的区别:

<figure class="table">

| 

**痛击**

 | 

**sh**

 |
| 

*   Bourne SHell again

 | 

*   Shell

 |
| 

*   Younaohu

 | 由斯蒂芬·伯恩开发的 T3 |
| 

*   嘘

 | 

*   The predecessor of Bashi

 |
| 

*   Bash is the default SHELL.

 | 

*   Sh is not the default SHEL

 |
| 

*   #!/bin/bash

 | 

*   #!/bin/sh

 |
| 

*   After the upgrade, the functions are richer.

 | 

*   Less functional.

 |
| 

*   Support job control.

 | 

*   Job control is not supported.

 |
| 

*   Bash is not a valid POSIX shell.

 | 

*   嘘是有效的 POSIX 外壳.

 |
| 

*   Easy to use

 | 

*   Not like a bash.

那么容易 |
| 

*   Not as portable as sh.

 | 

*   More portable than bash.

 |
| 

*   Extended language

 | 

*   Original language

 |
| 

*   Bash script is designed for Bash.

编写的脚本 | 

*   A Shell script is a script written in any Shell

 |
| 

*   Support command history.

 | 

*   Command history is not supported.

 |

</figure>