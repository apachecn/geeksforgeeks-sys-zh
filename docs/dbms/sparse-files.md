# 稀疏文件

> 原文:[https://www.geeksforgeeks.org/sparse-files/](https://www.geeksforgeeks.org/sparse-files/)

稀疏文件是一种计算机文件类型，它允许对大数据进行有效的存储分配。当文件的大部分数据为零(空数据)时，该文件被认为是稀疏的。
对这种文件的创建的支持通常由文件系统提供。这种类型的文件在计算机科学领域，如数据库管理系统、数字图像处理等，有着重要的用途。

**工作:**

稀疏文件的创建方式不同于普通(非空)文件。每当创建稀疏文件时，表示磁盘空块(字节)的元数据都会写入磁盘，而不是构成块的实际字节，从而使用更少的磁盘空间。这是因为空字节不需要保存，因此可以用元数据来表示。
只有当任何非空(零)数据写入文件时，才会写入实际数据块。当读取稀疏文件时，文件系统在运行时透明地将表示空块的元数据转换成用空字节填充的“真实”块。应用程序不知道这种转换，因为转换发生在文件系统级别。稀疏文件不需要完全填充空数据，而是文件的某些空部分也可以标记为稀疏。数据仍然遵循上述机制，但规模较小。

**稀疏文件的优势:**

*   无需物理写入任何扇区即可分配大量存储空间，因此可以更快地创建文件。
*   分配仅在写入非空数据时发生，因此节省了磁盘空间。
*   由于稀疏文件的逻辑空间大于分配的空间，因此可以读取比分配的更多的数据。
*   如果初始分配要求向空间写入全零，则不会发生实际分配，从而防止不必要的磁盘读写。
*   对于不完全稀疏的文件，它减少了首次写入的时间，因为系统不必为“跳过”的空间分配块。
*   在某些情况下，比文件压缩更好。

**稀疏文件的缺点:**

*   大多数文件复制操作都会破坏文件的稀疏属性。因此，文件的稀疏区域被显式分配到磁盘上，失去了它们的稀疏属性。
*   由于文件的逻辑大小可能大于其分配的大小，文件系统可用空间报告可能不正确。
*   一些应用程序不能有效地处理稀疏文件。
*   随着时间的推移，稀疏文件可能会随着有效的数据写入而变得碎片化