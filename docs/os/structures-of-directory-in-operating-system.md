# 操作系统中目录的结构

> 原文:[https://www . geesforgeks . org/操作系统目录结构/](https://www.geeksforgeeks.org/structures-of-directory-in-operating-system/)

一个**目录**是一个用来存放文件夹和文件的容器。它以分层的方式组织文件和文件夹。

![](img/abafd44c3c523c41d923db3196a99163.png)

目录有几种逻辑结构，如下所示。

*   **Single-level directory –** 
    The single-level directory is the simplest directory structure. In it, all files are contained in the same directory which makes it easy to support and understand. 

    但是，当文件数量增加或系统有多个用户时，单级目录有很大的局限性。因为所有文件都在同一个目录中，所以它们必须有一个唯一的名称。如果两个用户调用他们的数据集测试，那么就违反了唯一名称规则。

![](img/daab25a9a7aeac91597459a4a2005fbd.png)

**优势:**

*   由于它是一个单一的目录，所以它的实现非常容易。
*   如果文件较小，搜索将变得更快。
*   在这样的目录结构中，文件创建、搜索、删除、更新等操作非常容易。

**缺点:**

*   可能会有名称冲突的机会，因为两个文件可以有相同的名称。
*   如果目录很大，搜索将会很费时间。
*   这不能将同一类型的文件组合在一起。
*   **Two-level directory –** 
    As we have seen, a single level directory often leads to confusion of files names among different users. the solution to this problem is to create a separate directory for each user. 

    在两级目录结构中，每个用户都有自己的*用户文件目录(UFD)* 。ufd 有相似的结构，但每个都只列出单个用户的文件。每当有新用户登录时，系统的*主文件目录(MFD)* 就会进行搜索。MFD 由用户名或账号索引，每个条目都指向该用户的 UFD。

![](img/dea733a5bef1cbd856a8fcd465ba70f3.png)

**优势:**

*   我们可以给出完整的路径，如/用户名/目录名/。
*   不同的用户可以有相同的目录和文件名。
*   由于路径名和用户分组，文件搜索变得更加容易。

**缺点:**

*   不允许用户与其他用户共享文件。
*   尽管如此，它的可伸缩性并不是很高，两个相同类型的文件不能在同一个用户中组合在一起。

*   **树形结构目录–**
    一旦我们将两级目录看作高度为 2 的树，自然的概括就是将目录结构扩展到任意高度的树。
    这种一般化允许用户创建他们自己的子目录，并相应地组织他们的文件。

![](img/cb4659a06c327c107ce8dcee2e546112.png)

树形结构是最常见的目录结构。该树有一个根目录，系统中的每个文件都有一个唯一的路径。

**优势:**

*   非常一般，因为可以给出完整的路径名。
*   扩展性很强，名字碰撞的概率比较小。
*   搜索变得非常容易，我们既可以使用绝对路径，也可以使用相对路径。

**缺点:**

*   并非每个文件都适合分层模型，文件可能会保存到多个目录中。
*   我们不能共享文件。
*   这是低效的，因为访问一个文件可能会在多个目录下。

*   **Acyclic graph directory –** 
    An acyclic graph is a graph with no cycle and allows us to share subdirectories and files. The same file or subdirectories may be in two different directories. It is a natural generalization of the tree-structured directory. 

    它用于两个程序员在一个联合项目中工作，他们需要访问文件的情况。相关联的文件存储在子目录中，将它们与其他项目和其他程序员的文件分开，因为他们在一个联合项目中工作，所以他们希望子目录位于他们自己的目录中。公共子目录应该共享。所以这里我们使用非循环目录。

    需要注意的是，共享文件与复制文件不同。如果任何程序员在子目录中做了一些更改，它将反映在两个子目录中。

![](img/cb56eb4c1485fe4dfca9de60d7057b4a.png)

**优势:**

*   我们可以共享文件。
*   由于路径不同，搜索很容易。

**缺点:**

*   我们通过链接共享文件，以防删除文件会产生问题，
*   如果链接是软链接，那么在删除文件后，我们留下了一个悬空指针。
*   在硬链接的情况下，要删除一个文件，我们必须删除与之相关的所有引用。

*   **通用图目录结构–**
    在通用图目录结构中，允许在一个目录结构内循环，其中多个目录可以从多个父目录中派生。
    这种目录结构的主要问题是计算文件和目录占用的总大小或空间。

![](img/9e05ee27919bc91613600a9960f703f2.png)

**优势:**

*   它允许循环。
*   它比其他目录结构更灵活。

**缺点:**

*   它比其他的更贵。
*   它需要垃圾收集。