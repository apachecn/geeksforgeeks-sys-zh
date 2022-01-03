# 微处理器中的机器控制指令

> 原文:[https://www . geesforgeks . org/machine-control-in-instructions in-microprocessor/](https://www.geeksforgeeks.org/machine-control-instructions-in-microprocessor/)

这些类型的指令控制机器功能，如暂停、中断或不执行任何操作。这种类型的指令改变了处理器中执行的不同类型的操作。

以下是机器控制指令的类型:

```
1\. NOP (No operation)
2\. HLT (Halt)
3\. DI (Disable interrupts)
4\. EI (Enable interrupts)
5\. SIM (Set interrupt mask)
6\. RIM (Reset interrupt mask)
```

1.  **NOP(无操作)–**

```
Opcode- NOP
Operand- None
Length- 1 byte
M-Cycles- 1
T-states- 4
Hex code- 00
```

1.  不执行任何操作时使用。在执行 NOP 期间，没有任何标志受到影响。该说明用于填写时间延迟或在故障排除时删除和插入说明。

2.  **HLT(暂停并进入等待状态)–**

```
Opcode- HLT
Operand- None
Length- 1 byte
M-Cycles- 2 or more
T-states- 5 or more
Hex code- 76
```

1.  微处理器完成当前指令的执行，并停止任何进一步的执行。在 HLT 状态期间，寄存器的内容不受影响。

2.  **DI(禁用中断)–**

```
Opcode- DI
Operand- None
Length- 1 byte
M-Cycles- 1
T-states- 4
Hex code- F3
```

1.  当代码序列的执行不能被中断时，使用禁用中断。例如，在关键的时间延迟中，该指令在代码的开头使用，而中断在代码的结尾启用。不能禁用 8085 TRAP。

2.  **EI(启用中断)–**

```
Opcode- EI
Operand- None
Length- 1 byte
M-Cycles- 1
T-states- 4
Hex code- FB
```

1.  系统复位或确认中断后，触发器的中断使能复位，从而禁用中断。

2.  **SIM(设置中断屏蔽)–**

```
Opcode- SIM
Operand- None
Length- 1 byte
M-Cycles- 1
T-states- 4
Hex code- 30
```

1.  该 SIM 指令用于实现 8085 微处理器的不同中断，如 RST 7.5、6.5 和 5.5，以及串行数据输出。它不影响 TRAP 中断。

2.  **RIM(重置中断屏蔽)–**

```
Opcode- RIM
Operand- None
Length- 1 byte
M-Cycles- 1
T-states- 4
Hex code- 20
```

1.  这是一条多用途指令，用于读取 8085 中断 7.5、6.5、5.5 的状态，并读取串行数据输入位。