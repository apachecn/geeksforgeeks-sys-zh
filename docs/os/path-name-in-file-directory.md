# 文件目录中的路径名

> 原文:[https://www.geeksforgeeks.org/path-name-in-file-directory/](https://www.geeksforgeeks.org/path-name-in-file-directory/)

先决条件–[文件系统](https://www.geeksforgeeks.org/file-system-operating-systems/)

**分级目录系统–**

目录以树的形式维护。每个用户都可以拥有所需数量的目录，这样文件就可以以自然的方式组合在一起。

这种结构的优点:

*   搜索是有效的
*   文件摸索能力增强

当文件系统被组织为目录树时，需要某种方式来指定文件名。

通常使用两种不同的方法:

1.  **Absolute Path name –** In this method, each file is given an **absolute path** name consisting of the path from the root directory to the file. As an example, the path **/usr/ast/mailbox** means that the root directory contains a subdirectory usr, which in turn contains a subdirectory ast, which contains the file mailbox.

    绝对路径名总是从根目录开始，并且是唯一的。

    在 UNIX 中，路径的组件由“/”分隔。在 Windows 中，分隔符是“\”。
    **Windows**\ usr \ ast \邮箱
    **UNIX**/usr/ast/邮箱

2.  **Relative Path name –** This is used in conjunction with the concept of the **working directory** (also called the **current directory**).A user can designate one directory as the current working directory, in which case all path names not beginning at the root directory are taken relative to the working directory.

    对于**例**，如果当前工作目录为/usr/ast，那么绝对路径为/usr/ast/mailbox 的文件可以简单引用为 mailbox。
    换句话说，如果工作目录是/usr/ast，UNIX
    命令:**CP/usr/ast/mailbox . bak**
    和命令:**CP mailbox . bak**
    会做完全一样的事情。

**什么时候用哪种方法？**
有些程序需要访问特定的文件，而不考虑工作目录是什么。在这种情况下，它们应该总是使用绝对路径名。例如，拼写检查器可能需要阅读/usr/lib/dictionary 来完成它的工作。在这种情况下，它应该使用完整的绝对路径名，因为它不知道调用它时工作目录是什么。无论工作目录是什么，绝对路径名总是有效的。

当然，如果拼写检查器需要来自/usr/lib 的大量文件，另一种方法是发出系统调用，将其工作目录更改为/usr/lib，然后仅使用 dictionary 作为打开的第一个参数。通过显式更改工作目录，它肯定知道自己在目录树中的位置，因此可以使用相对路径。