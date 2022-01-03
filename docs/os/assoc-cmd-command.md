# 关联 cmd 命令

> 原文:[https://www.geeksforgeeks.org/assoc-cmd-command/](https://www.geeksforgeeks.org/assoc-cmd-command/)

**关联**是在窗口命令处理器命令提示符下找到的命令(内部)，允许文件扩展名与文件类型关联。文件扩展名通常是文件名中句点(“”)后的最后几个字符).尽管文件扩展名根本不是强制性的(对于无扩展名的文件)。

文件类型关联的扩展主要由 Windows 操作系统实施。其他操作系统，如 Linux 和 macOS，确实支持这种关联，但并没有将它们强制到 Windows 级别。Linux 内核利用幻数来识别文件类型。在本文中，我们将看看 cmd 中的 assoc 命令，并看看它的用法。

**命令描述:**

```
ASSOC [.ext[=[fileType]]]

 .ext      Specifies file extension to associate file type with
 fileType  Specifies file type to associate with file extension

```

键入不带参数的 ASSOC 以显示当前文件关联。如果仅使用文件扩展名调用 ASSOC，它将显示该文件扩展名的当前文件关联。不为文件类型指定任何内容，该命令将删除文件扩展名的关联。

**注意–**
执行 assoc /？命令行中的命令

**使用命令:**
显示文件类型关联的每个扩展名列表。要显示列表，请在 cmd 中执行以下命令。

**Assoc :**
执行后，输出显示为这样。

```
.001=WinRAR
.386=vxdfile
.3ds=Photoshop.3DSFileType.130
.3g2=WMP11.AssocFile.3G2
.3ga=VLC.3ga
.3gp=WMP11.AssocFile.3GP
.3gp2=WMP11.AssocFile.3G2
.3gpp=WMP11.AssocFile.3GP
.669=VLC.669
.7z=WinRAR
.8ba=Photoshop.PlugIn
.8bc=Photoshop.PlugIn 

```

显示单个文件扩展名的文件类型关联:

要显示关联，请运行以下命令。

```
assoc ext 
```

其中 ext 是我们想要获取信息的文件扩展名。

**示例:**
获取关于的关联信息。jpg 文件扩展名

```
assoc .jpg 
```

**输出:**

```
.jpg=jpegfile 
```

**注–**
延长前总要有句号。

**创建文件类型关联:**
要求 cmd 以提升的权限运行(管理员模式)。要创建与扩展名关联的文件类型，将使用以下命令。

```
assoc extension=filetype 
```

这里，扩展名是我们想要关联的文件扩展名，文件类型是我们想要关联该扩展名的类型。扩展名前面应该总是带句点/句号，扩展名和文件类型之间应该总是有一个等号(=)。

**示例:**
关联的命令。带有 pngfile 文件类型的 jkl 扩展。

```
assoc .jkl=pngfile 
```

*   应该注意的是，任何扩展名的关联都应该与已知的文件类型(操作系统已知的文件类型)相关联。否则，操作系统可能不知道该为特定文件类型分配哪个应用程序。
*   这是因为，正如扩展名与文件类型相关联一样，文件类型也与应用程序相关联。因此，如果用户选择新的文件类型，那么它就不会有与之相关联的应用程序(这可以通过使用 ftype 将应用程序与文件类型相关联来解决)。