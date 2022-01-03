# 计算机系统特点

> 原文:[https://www . geesforgeks . org/计算机系统特征/](https://www.geeksforgeeks.org/characteristics-of-computer-system/)

一个**计算机系统**是一个基本的和功能性的计算机，它包括所有的[硬件和软件](https://www.geeksforgeeks.org/difference-between-hardware-and-software/)，这些都是使它为用户所需要的。它是一种电子设备，接受数据作为输入，以预定的方式处理数据，然后将结果作为输出传送到屏幕上。

代表中央处理器的中央处理器是计算机的大脑。它是计算机内的电子电路，执行组成计算机程序的指令。中央处理器的各个模块是-

*   它执行算术和逻辑表达式的运算。
*   定时和控制单元控制在计算机系统上执行的整个操作。
*   寄存器是内置在中央处理器中的非常少量的非常快速的存储器，用于存储中央处理器正在执行的当前数据和指令。
*   存储单元是计算机系统的存储单元，用于存储程序语句和数据。
*   输入和输出单元发送和接收数据并显示给用户。

**计算机系统特点:**

1.  **数据总线的大小–**
    它定义了可以通过数据总线传输的位数。它也被称为数据总线的宽度。数据总线是双向的，因为微处理器可以从内存中读取数据或将数据写入内存。

*   **Size of Address Bus –**
    The size of address bus determines the capacity of CPU or micro-processor to identify different memory locations.

    ```
    Chip Size- 2(raised power R) * N
    Address Bus- 2(raised power R) 
    ```

    地址总线是单向的，因为微处理器正在寻址特定的存储单元。没有外部设备不能写入微处理器。

    *   **Word-length –**
    It is the amount of data that can be processed by CPU and micro-processor at a time. It depends on the data bus, register, ALU etc. For example, 8-bit processor can process 8 bit data at a time. A processor with larger word length can process data at a time with fastest speed as compared to processor with shorter word length.*   **Capability –**
    It depends upon the number of instructions a micro-processor have and the flexibility provided by each instruction.

    *   **Instruction Set –**
    It is the total number of instructions that a micro-processor can understand.*   **Band-Width –**
    It is the number of bits processed in a single instructions.*   **Data Types –**
    There are various types of data formats that can be handled by CPU or micro-processor such as binary, BCD, ASCII, Sign and Unsigned numbers.*   **Input-Output Addressing capability –**
    It depends upon the input-output addresses provided by input-output instruction.*   **Clock Speed –**
    The clock speed finds out the number of operations per second, the processor can perform. The CPU required a fix number of clock cycles to execute each instruction. The faster the clock, then CPU execute more instructions per second. It is expressed in MHz or GHz.

    ```
    1 MHz= 1 million cycles per second
    1 GHz= 1 billion cycles per second 
    ```

    <center>

    | 机器循环 | 时钟周期或测试状态 |
    | --- | --- |
    | 操作码提取 | 4T |
    | 读存储器 | 3T |
    | 存储写入 | 3T |
    | 输入输出读取 | 3T |
    | 输入输出写入 | 3T |

    </center>