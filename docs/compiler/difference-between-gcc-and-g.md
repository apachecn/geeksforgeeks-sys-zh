# GCC 和 G++

的区别

> 原文:[https://www.geeksforgeeks.org/difference-between-gcc-and-g/](https://www.geeksforgeeks.org/difference-between-gcc-and-g/)

[GCC](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/) 代表 [GNU 编译器集合](https://www.geeksforgeeks.org/gcc-command-in-linux-with-examples/)，主要用来编译 C 和 C++语言。也可以用来编译 Objective C 和 Objective C++。编译源代码文件时需要的最重要选项是源程序的名称，其余每个参数都是可选的，如警告、调试、链接库、对象文件等。GCC 命令的不同选项允许用户在不同阶段停止编译过程。

[g++命令](https://www.geeksforgeeks.org/compiling-with-g-plus-plus/)是 GNU c++编译器调用命令，用于对源代码进行预处理、编译、汇编和链接，生成可执行文件。g++命令的不同“选项”允许我们在中间阶段停止这个过程。

<u>**g++&gcc**T3 之间的差异</u>

| g++ | （同 groundcontrolcenter）地面控制中心 |
| g++用于编译 C++程序。 | gcc 用于编译 C 程序。 |
| g++可以编译任意**。c** 或**。cpp** 文件，但它们将仅被视为 C++文件。 | gcc 可以编译任意**。c** 或**。cpp** 文件，但它们将分别被视为 C 和 C++文件。 |
| 通过 g++编译 C++程序的命令是
**g++ fileName.cpp -o 二进制** | 通过 gcc 编译 C 程序的命令是
**gcc fileName.c -o 二进制** |
| 使用 g++链接目标文件，文件自动链接在标准 C++库中。 | gcc 不这样做。 |
| g++用更多预定义的宏编译。 | gcc 用更多数量的预定义宏编译 C++文件。其中一些是#define __GXX_WEAK__ 1、#define __cplusplus 1、# define _ _ 弃用 1 等 |