# 计算机网络中的乌托邦单纯形协议

> 原文:[https://www . geesforgeks . org/乌托邦-单工-计算机网络协议/](https://www.geeksforgeeks.org/utopian-simplex-protocol-in-computer-network/)

我们将考虑一个简单的协议，因为它不担心任何出错的可能性。数据只在一个方向上传输。两者都在传输，接收网络层始终准备就绪。处理时间可以忽略。有无限的缓冲空间。这种完全不切实际的协议，我们称之为“乌托邦”，只是为了展示我们将建立的基本结构。其实现如下所示。

**一个乌托邦式的单工协议:**
只有一个方向的数据传输从发送者到接收者。这里我们假设通信信道是无差错的，并且接收机将无限快速地处理输入。发送方以最快的速度将数据发送到线路上。

```
typedef enum {frame_arrival} event_type;

#include"protocol.h"

void sender1(void)
{
 frame s;                     /* buffer for an outbound frame */
 packet buffer;                /* buffer for an outbound packet */
 while(true)
 {
  from_network_layer(&buffer);   /* go get something to send */
  s.info=buffer;               /* copy it into s for transmission */
  to_physical_layer(&s);        /* send it on its way */
 }                           
}

void receiver1(void)
{
 frame r;
 event_type event;             /* filled in by wait, but not used here */
 while(true)
  {
   wait_for_event(&event);       /* only possibility is frame_arrival */
   from_physical_layer(&r);      /* go get the inbound frame */
   to_network_layer(&r.info);     /* pass the data to the network layer */
  }
}
```

这个协议有两个不同的程序，一个发送方和一个接收方。不需要 MAX_SEQ，因为没有使用序列号或确认。唯一可能的事件类型是帧到达(即未损坏帧的到达)。

发送方以最快的速度在无限循环中输出数据。循环体由三个动作组成，它们是–

*   从网络层获取数据包，
*   使用变量 s 构造一个出站帧，
*   把框架送过去。

其他字段与错误和流量控制有关，这里没有错误或流量控制限制，因此这里只使用信息字段。

接收器同样简单。当帧到达并且事件被设置为帧到达时，wait_for_event 过程返回。来自硬件缓冲区的新到达的帧被 from_physical_layer 的调用移除，并放入变量 r，以便接收器可以获得它。当数据部分被传递到网络层时，数据链路层返回等待下一帧，暂停自身直到帧到达。它既不处理流量控制，也不处理纠错，因此不现实。