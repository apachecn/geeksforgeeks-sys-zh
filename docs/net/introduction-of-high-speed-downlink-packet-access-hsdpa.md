# 高速下行分组接入介绍(HSDPA)

> 原文:[https://www . geesforgeks . org/introduction-of-high-speed-download-packet-access-HSDPA/](https://www.geeksforgeeks.org/introduction-of-high-speed-downlink-packet-access-hsdpa/)

**HSDPA** 代表高速下行分组接入。

它提供了更快的下载速度。它是对 UMTS 形式的升级。HSDPA 提供高达 7.2 Mbps 的下载速率。HSDPA 是一个增强的 3G 移动电话通信协议。3.5G、3G+或 turbo 3G，允许基于通用移动电信系统的网络具有更高的数据传输速度和容量。理论峰值速度为 14.4 Mbps。增加分组数据支持。提高下行分组数据的最大用户吞吐量。更低的数据包延迟。

改进的下行链路提供高达 14 兆比特/秒的传输速率，延迟显著降低。目前的设备支持 7.2 Mbps 的吞吐量。为了在对现有无线电接口协议架构影响最小的情况下支持 HSDPA 特征，引入了新的 MAC 子层 MAC-hs。它具有许多特性，如快速调度、快速链路自适应、短传输时间间隔等。它有自适应调制和编码技术。它有 HARQ 科技。它有 16QAM 调制。

**HSPDA 提供什么？**

*   **速度–**
    更快的下游吞吐量。它还支持下行链路中需要瞬时高数据速率的服务，例如互联网浏览。

*   **容量–**
    它以相对较低的成本将系统容量提高了 3-4 倍。

*   **减少延迟–**
    它减少了延迟，与 HSDPA 的往返时间可以减少到 100 毫秒以下

*   **网络覆盖–**
    现有站点上市时间短，不需要新站点。提高最终用户质量。

**HSPDA 使用的方法:**

```
1. Short transmission time interval (TTI)
2. Higher order modulation
3. Fast scheduling and user diversity
4. Fast link adaptation 
```

**HSDPA 的申请:**

*   HSDPA 有助于减少数据传输的时间延迟，提高系统吞吐量。
*   它优化了系统频谱效率。
*   使用 HSDPA 的体验和使用固网 ADSL 服务的体验也是非常相似的。
*   它特别适用于上下行非对称流量和突发数据流量。
*   快速调度
*   共享信道和多码传输

**HSDPA 是如何运作的？**
HSDPA 代表了 WCDMA 无线接口的演进，其使用的方法很少类似于 EDGE(增强数据速率用于 GSM 演进)技术用于 GSM 无线接口的方法。
能够在降低延迟的情况下提高数据吞吐量和容量的基本特性如下:

*   用户的时间和代码复用。
*   多码传输。
*   固定扩频因子(SF = 16)。
*   较短的 TTI = 2 毫秒。
*   数据通道无 DTX(不连续传输)。
*   没有电源控制。
*   没有软切换。

HSDPA 的运作步骤是:

1.  用户设备通过 HS-DPCCH(高速专用物理控制信道)报告 CQI。
2.  节点 B 使用高速信令控制信道来确定哪个用户设备将被服务。
3.  节点 B 通知用户设备使用高速信令控制信道进行服务。
4.  数据通过 HS-DSCH(高速下行共享信道)传输。
5.  用户设备通过 HS-DPCCH(高速专用物理控制信道)进行确认。

**HSDPA 特色:**

```
1. Adaptive modulation and coding (AMC)
2. Multi-code operation
3. Hybrid automatic repeat request (HARQ)
4. Higher order modulation
5. Short transmission time interval
6. Fast link adaptation
7. Fast scheduling
```

**HSDPA 优势**

*   它增加了无线电容量。
*   网络可以采用给实时应用程序更高优先级的数据调度器，
*   它在下行方向给出最高的数据负载。
*   采用较短的帧长度可以更快地对无线信道中的问题做出反应。
*   它提供了更短的延迟，支持新的应用，如交互式网络游戏。
*   移动运营商可以与使用 HSDPA 的无线网络竞争，因为他们不需要分布式接入点。
*   它最适合带宽高度可变的应用。

**HSDPA 的劣势:**

*   HSDPA 将使 3G 网络每次都以更高的负载率运行。因此这增加了现有 UMTS 上的噪声，然后降低了 UMTS 容量。
*   不适合对带宽要求较低的应用，如语音。
*   没有软切换，因此微微小区在同一建筑物中重叠，并将产生自干扰
*   HSDPA 仅支持在下行链路上使用 UMTS 网络。