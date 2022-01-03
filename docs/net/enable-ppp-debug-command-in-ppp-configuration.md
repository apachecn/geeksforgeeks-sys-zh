# 在 PPP 配置

中启用 PPP 调试命令

> 原文:[https://www . geesforgeks . org/enable-PPP-debug-command-in-PPP-configuration/](https://www.geeksforgeeks.org/enable-ppp-debug-command-in-ppp-configuration/)

对于指定的[点对点协议(PPP)](https://www.geeksforgeeks.org/ppp-full-form/) 接口，**启用 PPP 调试命令**顾名思义，一般会启用所有的调试选项。如果未指定 port 参数，则调试信息或数据通常会传输到通常输入命令的端口或 telnet 会话，否则会传输到指定的 PORT 参数。

该命令包含几个参数。下面给出了一些参数:

**DEBUG 参数:**
这个参数一般需要指定需要禁用哪些调试选项。该参数的值通常是单个项目，或者基本上是各种项目的逗号分隔列表。下表给出了一些[点对点协议(PPP)](https://www.geeksforgeeks.org/ppp-full-form/) 调试选项:

<center>

| [计]选项 | 描述 |
| --- | --- |
| 全部 | 表示所有可用的调试选项。 |
| 作家（author 的简写） | 表示 PPP 身份验证。如果链路控制协议在链路或连接上打开，但网络协议仍处于关闭状态，则最常见的原因是身份验证失败。 |
| BAPPKT | 表示通常通过接口接收的 BAP 数据包。 |
| 贝州 | 表示 BAP 状态机的所有转换。 |
| 回收 | 表示回调状态机的所有转换。 |
| 要求 | 表示仅导致按需链接被激活的所有数据包。 |
| 编码指令 | 表示 ENCO 状态机通常只需要控制和处理与 ENCO(即加密/压缩模块)的连接和分离。 |
| 人员登陆艇(Landing Craft Personnel) | 表示 LCP 状态机的所有转换。 |
| 新型冠状病毒肺炎（Novel coronavirus pneumonia） | 代表 NCP 状态机的所有转换。 |
| 包 | 表示在 PPP 接口上接收和传输的所有数据包。 |
| 利用 | 仅表示每个下层接口的利用率度量和总体利用率。 |

*   **PORT 参数:**
    该参数一般用于指定需要向其传输或发送调试输出的异步端口。这通常可以在脚本中启用调试。每次输入“启用 PPP 调试”命令时，都会使用此规则计算调试输出的目标。
*   **超时参数:**
    该参数一般要求指定调试结束或自动停止的时间(秒)。默认值设置为 NONE。如果此参数指定了 NONE，则应手动禁用调试。
*   **NUMPKTS 参数:**
    这个参数一般需要指定调试停止前需要显示的数据包数量，只是为了 PKT 调试。默认值设置为 CONT。数据包调试将无限期继续，如果此参数指定了 CONT，则应手动禁用。

**语法–**

```
ENABLE PPP=ppp-interface 
DEBUG={UTILISATION|CALLBACK|ENCO|NCP
        |AUTH|DEMAND|BAPPKT||BAPSTATE|LCP|ALL}
         [, ...] 
 [PORT=port-number] [TIMEOUT={NONE|1..4000000000}]
 [NUMPKTS={CONT|1..4000000000}]
```

在这里，

*   **ppp-接口:**代表 PPP 接口数量。
*   **端口号:**表示路由器上异步端口的总数。

</center>