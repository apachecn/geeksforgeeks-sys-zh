# 操作系统中的文件访问方法

> 原文:[https://www . geesforgeks . org/file-access-methods-in-operating-system/](https://www.geeksforgeeks.org/file-access-methods-in-operating-system/)

先决条件–[文件系统](https://www.geeksforgeeks.org/file-system-operating-systems/)
当使用一个文件时，信息被读取并访问到计算机内存中，有几种方法可以访问该文件的信息。有些系统只提供一种文件访问方法。其他系统，如 IBM 的系统，支持许多访问方法，为特定的应用程序选择合适的方法是一个主要的设计问题。

将文件访问到计算机系统中有三种方法:顺序访问、直接访问、索引顺序方法。

1.  **Sequential Access –** 
    It is the simplest access method. Information in the file is processed in order, one record after the other. This mode of access is by far the most common; for example, editor and compiler usually access the file in this fashion. 

    读写是文件操作的主要部分。读取操作*-读取下一个-* 读取文件的下一个位置，并自动前进一个文件指针，该指针跟踪输入/输出位置。同样，对于-write *next-* 追加到文件的末尾并前进到新编写的材料。

    **要点:**

    *   数据是按顺序一个记录接一个记录地访问的。
    *   当我们使用读命令时，它将指针向前移动一位
    *   当我们使用 write 命令时，它会分配内存并将指针移动到文件的末尾
    *   这样的方法对胶带来说是合理的。

2.  **直接访问–**
    另一种方法是*直接访问方法*也称*相对访问方法*。一种字段长度的逻辑记录，允许程序快速读写记录。没有特别的顺序。直接访问基于文件的磁盘模型，因为磁盘允许随机访问任何文件块。对于直接访问，文件被视为块或记录的编号序列。因此，我们可以先读取块 14，然后读取块 59，然后写入块 17。对于直接访问文件的读写顺序没有限制。
    用户提供给操作系统的块号通常是*相对块号*，文件的第一个相对块是 0，然后是 1，以此类推。

3.  **Index sequential method –** 
    It is the other method of accessing a file that is built on the top of the sequential access method. These methods construct an index for the file. The index, like an index in the back of a book, contains the pointer to the various blocks. To find a record in the file, we first search the index, and then by the help of pointer we access the file directly. 

    **要点:**

    *   它建立在顺序访问的基础上。
    *   它通过使用索引来控制指针。