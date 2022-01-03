# 如何提取和拆解一个 Linux 内核

> 原文:[https://www . geesforgeks . org/如何提取和分解一个 linux 内核/](https://www.geeksforgeeks.org/how-to-extract-and-disassemble-a-linux-kernel/)

如果您想要寻找一些有故障的代码或者想要检查各种函数的入口点，提取和检查 Linux 内核的反汇编代码会非常有帮助。一旦你知道了所需的必要工具，这个过程就相当直观了。

下面描述的过程适用于 Ubuntu 20.04，但也适用于其他基于 GNU/Linux 的操作系统。我们将使用所有 Ubuntu 发行版预装的 **objdump** 命令行工具。要检查它是否已安装并工作，请在您的终端上键入以下内容，您应该会看到有关该程序的版本和许可证信息。

```
objdump --version
```

Linux 内核可执行文件叫做 **vmlinuz** 。这是我们启动计算机时首先加载到内存中的可执行文件，这就是我们要分解的内容。该文件位于 **/boot/** 目录下。然而，它是压缩的。在使用 linux 头文件附带的 **extract-vmlinux** 脚本进行反汇编之前，我们必须先提取它。

**步骤 1:将压缩的内核可执行文件复制到不同的位置:**
首先，我们将创建一个内核副本到我们选择的位置，并将 **cd** 放入该目录。此步骤需要超级用户权限。

```
mkdir ~/kernel-tmp
sudo cp /boot/vmlinuz-$(uname -r) ~/kernel-tmp
cd kernel-tmp
```

**步骤 2:提取内核:**
现在我们将提取已经复制到我们目录中的压缩内核。我们将使用 linux 头文件附带的 **extract-vmlinux** 脚本。

```
sudo /usr/src/linux-headers-$(uname -r)/scripts/extract-vmlinux vmlinuz-$(uname -r) > decomp-vmlinuz
```

上面的命令将为我们的内核副本运行 **extract-vmlinux** 脚本，并将其输出到名为**反编译-vmlinuz** 的文件中，该文件将位于我们当前的工作目录下。

**STEP 3:反汇编:**
我们现在准备反汇编解压缩后的可执行文件。只需运行以下命令

```
objdump -D decomp-vmlinuz > disassembled-vmlinuz.asm
```

分解后的内核代码现在可以在**diss assembly-vmlinuz . ASM**文件中找到。

**STEP 4:寻找符号:**
被拆解的内核文件没有符号，因此我们不能很容易地找到函数的起点。Linux 将所有符号名称及其起始地址存储在一个单独的文件中。为了便于访问，我们也将复制该文件。

```
sudo cp /boot/System.map-$(uname -r) ./
```

现在，我们可以很容易地在**system . map-x . x-xx-generic**文件中对我们的符号名称进行 grep，以获得起始地址，然后我们可以在**diss assembly-vmlinuz . ASM**文件中查找该地址。
例如，我们可以申请**register _ keyboard _ notifier**

```
sudo cat System.map-$(uname -r) | grep register_keyboard_notifier
```

这将给出类似如下的输出:

```
ffffffff816ec720 T register_keyboard_notifier
```

我们可以复制起始地址，并在反汇编的内核代码中搜索它，以找到如下内容:

```
ffffffff816ec720:    e8 4b 13 98 ff           callq  0xffffffff8106da70
ffffffff816ec725:    55                       push   %rbp
ffffffff816ec726:    48 89 fe                 mov    %rdi,%rsi
ffffffff816ec729:    48 c7 c7 a0 f7 d8 82     mov    $0xffffffff82d8f7a0,%rdi
ffffffff816ec730:    48 89 e5                 mov    %rsp,%rbp
ffffffff816ec733:    e8 18 bb 9d ff           callq  0xffffffff810c8250
...
```