# cmd | Rem 命令

> 原文:[https://www.geeksforgeeks.org/cmd-rem-command/](https://www.geeksforgeeks.org/cmd-rem-command/)

Rem(缩写为*备注*)是在 Windows 命令处理器*命令提示符*中找到的命令(内部)，允许在批处理程序中包含注释。大多数编程语言通常通过与其相关联的特殊语法来支持注释。《出埃及记》Python 使用井号/hashtag ( #)来表示内联注释。Rem 命令用于*内联*注释，因此该注释仅在当前行结束前有效(或第一次出现 **CRLF** )，尽管可以在单独的行上使用多个 Rem 命令创建多行注释。在本文中，我们将看一下 Rem 命令，并了解它的各种用途。

**命令描述:**

```
Records comments (remarks) in a batch file or CONFIG.SYS.

REM [comment] 
```

**执行* **rem /，即可获得以上输出？** *命令行中的命令*

**使用命令:**
注释通常用于向代码中添加更多的英特尔信息。它有助于洞察代码的创建者在写代码时在想什么。它对于提供一些与代码相关的指针或附录也很有用。注释作为一种人类可读的代码形式，总体上有助于降低代码的复杂性。它们也有助于引导不了解这种语言的读者。例如，让我们看一下下面的代码片段:

```
@echo off

echo %~f0
echo %~t0

```

对于从未见过上述语法的人来说，代码一开始可能相当神秘。但是如果在代码中添加注释:

```
REM Used to disable echo of command entry and current working directory
@echo off

REM Displaying the full path (absolute Path) of the this file
echo %~f0

REM Displaying the timestamp of creation of this file
echo %~t0

```

代码的功能变得清晰，人们可以很容易地指导它的工作。

**创建内联注释:**
可以通过在行首使用 REM 命令，然后键入注释来创建内联注释。

例如，

```
REM This code will display hello world
echo hello world!

```

内联注释也可以通过使用& REM 构造添加到行尾(前面有一些代码)。

例如，

```
echo Hello World! & REM This code will display hello world

```

**创建多行注释:**
可以使用跨多行的多个 rem 命令创建多行注释。

例如，

```
REM This code will tell the current time
REM The resolution of the time will be until milliseconds
REM The time will be based on the current timezone
echo | time

```

**注–**
评论创作也通过各种其他方式存在。《出埃及记》还有其他类型的*~注释*允许在声明之间进行注释。但是它们不是注释代码的记录方式，并且由于其他命令/语法的变通方法而存在。同样，这些也不在本文的讨论范围之内。