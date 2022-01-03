# 在 PPP 配置中添加 PPP 命令

> 原文:[https://www . geesforgeks . org/add-PPP-command-in-PPP-configuration/](https://www.geeksforgeeks.org/add-ppp-command-in-ppp-configuration/)

要使用一个物理层，ADD 命令，顾名思义就是要求添加同步端口、 [ISDN](https://www.geeksforgeeks.org/integrated-services-digital-network-isdn/) 呼叫、ACC 呼叫、MIOX 电路等。只需转到[点对点协议(PPP)](https://www.geeksforgeeks.org/ppp-full-form/) 接口。该命令包含几个参数。下面给出了一些参数:

1.  **OVER 参数:**
    需要指定 PPP 接口将要运行的物理接口。
2.  **认证参数:**
    要求指定物理接口或通道需要的认证协议。在这种情况下，如果指定了 CHAP，则使用[挑战握手身份验证协议(CHAP)](https://www.geeksforgeeks.org/challenge-handshake-authentication-protocol-chap/) ，如果指定了 PAP，则使用[密码身份验证协议(PAP)](https://www.geeksforgeeks.org/password-authentication-protocol-pap/) ，如果指定了 none，则不需要任何身份验证协议，等等。
3.  **CBDELAY 参数:**
    要求以十分之一秒为单位，指定取消回叫呼叫和一般回叫对等方之间的延迟。

*   **CBMODE 参数:**
    需要指定在 LCP 协商过程中是否进行或接受回调请求。*   **CBNUMBER 参数:**
    要求在 CBOPERATION 参数设置为 E164NUMBER 的情况下，指定请求回叫请求时必须包含的总数。*   **COMPALGORITHM 参数:**
    需要指定在压缩和解压缩 PPP 包时要使用的压缩算法。*   **CBOPERATION 参数:**
    需要指定需要包含在回叫请求中的回叫操作，以简单的向对等方指定如何确定和识别回叫号码。*   **压缩参数:**
    需要为正在添加的物理接口启用并允许压缩。*   **配置参数:**
    需要设置在采取某个动作之前发送或传输的配置请求总数。*   **LQR 参数:**
    需要设置 LQR 定时器。*   **MODEM 参数:**
    需要指定同步 MODEM 控制的状态。

    *   **NUMBER 参数:**
    需要指定需要添加的物理接口总数。*   **预校验参数:**
    需要指定需要用于预测器压缩的循环冗余校验类型。*   **重启参数:**
    需要指定未确认的配置请求或终止请求连续重传的时间。*   **stack check 参数:**
    需要指定用于 stack LZS 压缩算法的检查模式。*   **TERMINATE 参数:**
    需要设置当简单地试图关闭或结束链路时发送或传输的终止请求的总数，然后才假设或认为链路断开。*   **TYPE parameter :**
    It is required to specify the actual role of the physical interface simply for bandwidth on demand and leased line backup.

    **语法–**

    ```
    ADD PPP=ppp-interface OVER=physical-interface
        [ AUTHENTICATION = { PAP|NONE|CHAP|EITHER } ] 
        [AUTHMODE={IN|OUT|INOUT}] [CBDELAY=1..100] [CBMODE={REQUEST|OFF|ACCEPT}] 
        [CBNUMBER=e164number] [CBOPERATION={USERAUTH|E164NUMBER}] 
        [COMPALGORITHM={STACLZS|PREDICTOR}] [COMPRESSION={OFF|LINK}]
        [CONFIGURE={CONTINUOUS|value}] [LQR={time|ON|OFF}] 
        [MAGIC={OFF|ON}] [MODEM={OFF|ON}]
        [NUMBER=number] [PREDCHECK={CRCCCITT|CRC16}]
        [RESTART=time] [STACCHECK={SEQUENCE|LCB}] 
        [TERMINATE={CONTINUOUS|value}] [TYPE={DEMAND|SECONDARY|PRIMARY}]

    ```

    在这里，

    *   **PPP-接口=**
        PPP 接口号。
    *   **物理接口=**
        SYNn、ISDN-callname、ACC-callname、MIOXn-circuitname、TNL-callname 或 TDM-groupname。
    *   **e164number=**
        包含 0-9 位数字的电话号码，只需在执行回拨时拨打即可。
    *   **值=**
        重试阈值。
    *   **时间=**
        定时器值以秒为单位。
    *   **数量=**
        需要增加的 PPP 接口数量。