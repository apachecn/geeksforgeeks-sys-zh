# 【COMP 和 COMP3 的区别

> 原文:[https://www . geeksforgeeks . org/comp-and-comp 3 之差/](https://www.geeksforgeeks.org/difference-between-comp-and-comp3/)

计算机内部以多种形式存储数据。Cobol 语言便于程序员根据需要指定数据的内部表示。Cobol 有两种内部形式:

1.  **DISPLAY–**
    这是数据的默认内部表示。任何类型的数据都可以用 DISPLAY 内部表示来指定。
2.  **计算–**
    只有数值数据可以用计算内部表示来指定。有许多类型的计算表示，如 COMP，COMP-1，COMP-2，COMP-3 等。

USAGE 子句用于指定内部表示的类型。除了 66 或 88，您可以为 USAGE 子句使用任何级别号。

```
Syntax:
        USAGE IS {COMPUTATIONAL/COMP/DISPLAY}.
```

**1。
用法条款仅适用于数字数据项。它完全以二进制形式表示数据。并且可以根据数据的大小以半字或全字存储数据。在数据声明过程中，我们只能使用 9 和 S:**

*   9 用于存储声明整数变量。
*   s 用于存储标志。

**2。COMP3 :**
使用条款仅适用于数字数据项。它以打包的十进制形式存储数据。它使用最右边的一位来存储符号，而不管我们在 PIC 子句中是否使用了 S。十六进制数 C 和 F 在最右位存储正号，D 在最右位存储负号。在数据申报时，我们可以在 PIC 子句中使用 9、S 和 V。

v 用于存储数据项中特定位置的小数点。

【COMP 和 COMP3 的区别:

<figure class="table">

| 

免费票

 | 

COMP3

 |
| --- | --- |
| 它以纯二进制形式表示数据。 | 它以打包的十进制形式表示数据。 |
| 我们在 PIC 条款中只能使用 9 和 S。 | 我们可以在 PIC 条款中使用 9、S、V。 |
| COMP 用法根据数据的大小，以半字或全字存储数据。 | COMP3 用法以半字节(即 4 位)存储 1 位，并为符号保留单独的 1 位，符号存储在数据的右侧。 |
| 根据长度由数据占用的存储器是预先定义的，即:

*   9(01)-9(04):16 位(2 字节)
*   9(05)-9(09):32 位(4 字节)
*   S9(10)–S9(18):64 位(8 字节)

 | 数据占用的内存由以下公式定义:

*   (变量长度+ 1)/2 字节。

示例:S9(3)占用的内存为:(3+1)/2 i.e. 2 字节。 |
| COMP 不占用额外的空间来存储标志。 | 在 COMP3 中，强制登录存储在右侧，因此会占用额外的空间。 |
| 

```
Example:
        02 CompVariable PIC 9 USAGE IS COMP.
        02 CompVariable1 PIC S9(5) USAGE IS COMP.
```

 | 

```
Example:
        02 Variable PIC 9 USAGE IS COMP3.
        02 Variable1 PIC S9(10) USAGE IS COMP3.
        02 Variable2 PIC S9V99 USAGE IS COMP3.
```

 |

</figure>