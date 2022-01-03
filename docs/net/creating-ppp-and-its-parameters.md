# 创建购买力平价及其参数

> 原文:[https://www . geesforgeks . org/creating-PPP-及其参数/](https://www.geeksforgeeks.org/creating-ppp-and-its-parameters/)

通过同步端口、ISDN 呼叫、MIOX 电路、ACC 呼叫和 TDM 组(被称为物理层)，顾名思义，CREATE Command 用于开发和创建正在运行的指定 PPP 接口。

该命令包含几个参数。下面给出了一些参数:

*   **OVER 参数:**
    该参数简单指定了 PPP 接口运行的物理接口。与此同时，借助 ADD PPP 命令，我们还可以添加额外的物理接口。
*   **身份验证参数:**
    该参数指定了需要在物理接口或通道上使用的身份验证协议。
    在这种情况下，如果指定了 CHAP，则使用 CHAP(挑战握手认证协议)，如果指定了 PAP，则使用 PAP(密码认证协议)，如果指定了 none，则不需要任何认证协议，等等。

*   **AUTHMODE 参数:**
    该参数指定了对对等方的身份验证请求仅受 ISDN 或 ACC 呼叫方向的影响。
    当该参数被设置为 NONE 以外的值，并且物理接口基本上是 ISDN 或 ACC 时，则只有 AUTHMODE 参数有效。*   **BAP 参数:**
    指定是否需要 BAP(带宽分配协议)来简单协商需求 PPP 链路的激活。*   **BAPMODE 参数:**
    该参数指定哪个对等体发起另一个链接，只是为了添加到多链路束中。*   **CBDELAY 参数:**
    该参数指定了取消回叫呼叫和实际回叫对等方之间的延迟。*   **CBMODE 参数:**
    在 LCP 协商过程中，该参数指定是否进行回拨或者只是接受回拨。*   **CBNUMBER 参数:**
    该参数指定当简单地用设置为 E164NUMBER 的 CBOPERATION 参数请求回调时需要包含的总数。*   **CBOPERATION 参数:**
    该参数指定需要包含在回叫请求中的回叫操作，只是为了确定和向对等方指定如何确定和识别回叫号码。*   **COMPALGORITHM 参数:**
    该参数指定在压缩和解压缩 PPP 数据包时使用的压缩算法。

    *   **压缩参数:**
    该参数仅针对接口启用或禁用压缩要求。*   **配置参数:**
    该参数设置在采取任何措施之前正在传输或发送的配置请求总数。*   **调试字节参数:**
    此参数指定仅当启用并允许数据包调试选项时，为每个数据包显示的最大字节数。*   **描述参数:**
    为了更容易和简单地区分 PPP 接口的数量，该参数指定了用户定义的接口描述。*   **停机时间参数:**
    该参数以秒为单位指定时间，在任何通道关闭之前，PPP 接口应该将总利用率简单地表示为低于 download rate 参数指定的阈值的百分比。*   **ECHO 参数:**
    该参数指定是否需要 LCP Echo Request 和 Echo Reply 消息来确定或识别链路质量。*   **加密参数:**
    该参数仅针对接口启用或禁用加密要求。*   **FRAGMENT 参数:**
    该参数决定数据包是否被分段，这些参数仅适用于多链路捆绑接口。*   **fragment overhead 参数:**
    此参数指定允许开销的最大数量，简单来说就是百分比，仅用于借助可变分片方案对数据包进行分片，通常用于多链路 PPP。*   **IDLE 参数:**
    该参数控制和处理按需拨号功能。

    *   **IPREQUEST 参数:**
    在 IPCP 协商过程中，该参数指定是否对 IP 地址进行请求，以便对等方分配。*   **LQR 参数:**
    该参数设置 LQR 定时器。默认设置为开。*   **MAGIC 参数:**
    该参数启用或禁用幻数选项的协商。默认设置为开。*   **MODEM 参数:**
    该参数指定同步 MODEM 控制的状态。*   **NUMBER 参数:**
    该参数指定需要创建和开发的物理接口总数。*   **nullfragmiter 参数:**
    此参数指定在通过链路或连接发送 NULL 片段之前，多链路捆绑包中的链路可以空闲的最长时间(秒)。*   **PASSWORD 参数:**
    该参数指定当对等方在 CHAP 或 PAP 的帮助下请求身份验证时简单使用的密码。*   **预校验参数:**
    该参数指定预测器压缩所需的循环冗余校验类型。*   **重启参数:**
    该参数指定所有未确认的配置请求或终止请求的连续重传之间的时间。*   **堆叠检查参数:**
    该参数指定堆叠 LZS 压缩算法所需的检查模式。

    *   **星实体参数:**
    该参数指定了星实体以及加密算法，以便由 PPP 接口配置的加密通道使用。*   **TYPE 参数:**
    该参数简单地为按需带宽和租用线路备份指定了物理接口的主要作用。*   **正常运行时间参数:**
    该参数指定在额外通道打开之前，PPP 接口应包含利用率的时间(以秒为单位)，简单地表示为刚好高于 UPRATE 参数指定的阈值的百分比。*   **USERNAME parameter :**
    This parameter specifies the username that is being required when generating PAP authentication requests and also when responding to CHAP authentication challenges.

    **创建 PPP 的语法:**

    ```
    CREATE PPP=ppp-interface OVER=physical-interface 
    [AUTHENTICATION={EITHER|CHAP|NONE|PAP}]
    [AUTHMODE={IN|OUT|INOUT}] [BAP={OFF|ON}] 
    [BAPMODE={CALLBACK|CALL}] [CBDELAY=1..100] 

    [CBMODE={REQUEST|OFF|ACCEPT}] [CBNUMBER=e164number] 
    [CBOPERATION={USERAUTH|E164NUMBER}] 
    [COMPALGORITHM={STACLZS|PREDICTOR}]

    [COMPRESSION={OFF|ON|LINK}] [CONFIGURE={CONTINUOUS|value}] 
    [DEBUGMAXBYTES=16..256] [DESCRIPTION=description] [DOWNRATE=0..100] 
    [DOWNTIME=time] [ECHO={OFF|ON|period}] [ENCRYPTION={OFF|ON}] 
    [FRAGMENT={OFF|ON}] [FRAGOVERHEAD=0.100] [IDLE={OFF|ON|time}] 
    [IPREQUEST={OFF|ON}] [LQR={OFF|ON|time}] [MAGIC={OFF|ON}] 
    [MODEM={OFF|ON}] [NULLFRAGTIMER=time] [NUMBER=number] 
    [PASSWORD=password] [PREDCHECK={CRCCCITT|CRC16}] [RESTART=time] 
    [STACCHECK={SEQUENCE|LCB}] [STARENTITY=1..255] 
    [TERMINATE={CONTINUOUS|value}] 

    [TYPE={PRIMARY|SECONDARY|DEMAND}] [UPRATE=0..100] [UPTIME=time] 
    [USERNAME=username]

    ```

    **以上语法描述:**

    *   **PPP-接口–**
        PPP 接口号。
    *   **物理接口–**
        ACC-call name、SYNn、ISDN-callname、TNL-callname、MIOXn-circuitname 或 TDM-groupname。
    *   **e 164 number–**执行回拨时需要拨打的电话号码。
    *   **值–**
        重试阈值。
    *   **描述–**
        字符串，长度 1 至 70 个字符。
    *   **时间–**
        计时器值，单位为秒。
    *   **句点–**
        1 到 4294967295 之间的十进制数字。
    *   **数量–**
        创建或开发所需的 PPP 接口数量。
    *   **密码–**
        认证所需的密码，全长 1-32 个字符。
    *   **用户名–**
        认证所需的用户名，总长度为 1-32 个字符。