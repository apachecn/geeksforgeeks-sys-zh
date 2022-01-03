# 流式传输存储的视频

> 原文:[https://www.geeksforgeeks.org/streaming-stored-video/](https://www.geeksforgeeks.org/streaming-stored-video/)

**视频流**包括在服务器上存储预先录制的视频。

*   用户向这些服务器发送请求。
*   用户可以从头到尾观看视频，也可以随时暂停，向前或向后跳过，或者随时停止视频。

有 3 种视频流类别:

```
1. UDP Streaming
2. HTTP Streaming
3. Adaptive HTTP Streaming 
```

通常，今天的系统采用 HTTP 和自适应 HTTP 流。

这三种流技术的共同特点是广泛使用**客户端缓冲**。

**客户端缓冲的优势:**

1.  客户端缓冲区吸收服务器-客户端延迟的变化。在客户端收到延迟的数据包之前，将播放已接收但尚未播放的视频。
2.  即使带宽下降，用户也可以观看视频，直到缓冲区完全耗尽。

**1。UDP STREAMING:**
UDP 服务器根据客户端的消耗速率向客户端发送视频块(块:包含控制信息或用户数据的信息单位)。它以一定的速率传输数据块，该速率与客户端的视频消耗速率相匹配，方法是在稳定状态下通过 UDP 输出视频数据块。

例如，

```
Video consumption rate = 2Mbps
Capacity of one UDP packet = 8000 bits

Therefore, 
Transmission rate = 8000 bits/2 Mbps = 4000 msec 
```

**属性:**

*   UDP 不使用拥塞控制机制。视频块在使用 RTT(实时传输)协议传输之前被封装。
*   维护额外的客户机-服务器路径，以向服务器通知客户机状态，如暂停、继续、跳过等。

**缺点:**

*   带宽是不可预测的，并且在客户机和服务器之间变化。
*   UDP 流需要一个独立的媒体控制服务器，如 RTSP 服务器(实时流协议)来跟踪客户端状态(暂停、恢复等)。
*   设备配置了防火墙来阻止 UDP 流量，从而防止接收到客户端的 UDP 数据包。

**2。HTTP STREAMING:**
视频作为一个简单的普通文件存储在 HTTP 服务器中，并有唯一的 URL。客户机与服务器建立 TCP 连接，并发出对该网址的 HTTP GET 请求。服务器发送视频文件和一个 HTTP 响应。现在客户端缓冲区抓取视频，然后显示在用户屏幕上。

**优势:**

*   通过使用超文本传输协议，视频可以很容易地穿越防火墙和网络设备。
*   不需要像 RTSP 服务器那样的任何媒体控制服务器，从而降低互联网上大规模部署的成本。

**缺点:**

*   视频录制和播放之间的延迟或滞后。这会让观众更加恼火和恼怒。只有几毫秒的延迟是可以接受的。*   视频的早期预取，但是，如果用户在早期停止播放视频呢？不重视数据的浪费。*   All clients receive the same encoding of the video, despite the large variations in bandwidth amount available to different clients and also for same client over time.

    **用途:**
    Youtube 和网飞使用 HTTP 流机制。

    **3。自适应 HTTP 流:**
    HTTP 流的主要缺点，导致开发了一种新型的基于 HTTP 的流，称为 DASH(动态自适应 HTTP 流)。视频被编码成不同的比特率版本，具有不同的质量。主机从不同的位版本发出几秒钟长的动态视频请求。当带宽较高时，接收到高比特率块，因此在低带宽期间接收到高质量类似的低质量视频。

    **优势:**

    *   DASH 使用用户在屏幕上切换不同质量的视频。
    *   客户端可以使用 HTTP 字节范围请求来精确控制本地缓冲的预取视频量。
    *   DASH 还通过唯一的网址以不同的质量和不同的比特率存储不同版本的音频。

    因此，客户端动态选择视频和音频块，并在播放过程中进行本地同步。

    **用途:**
    COMCAST 使用 DASH 来流式传输高质量视频内容。