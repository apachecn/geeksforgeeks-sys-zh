# HRRN 调度全表

> 原文:[https://www.geeksforgeeks.org/hrrn-scheduling-full-form/](https://www.geeksforgeeks.org/hrrn-scheduling-full-form/)

**HRRN** 代表**最高响应比次**。

![HRRN-Full-Form](img/55ba3c0b6b462b8a433cd11430a1acce.png)

HRRN 调度是非抢占式调度，即非抢占式调度是每个作业的优先级取决于其估计运行时间和等待时间的调度。他们等待的时间越长，他们获得的优先权就越高，这防止了饥饿的过程。也就是说，响应率应该关注请求服务时间和等待时间。HRRN 不适合优先系统。

```
W = Waiting time of the process so far
B = Burst time or Service time of the process
```

![](img/99e15069e7e4215286af76c5d84584d1.png)

#### 算法程序

*   开始了。
*   它只考虑到达时间、突发时间和优先级的过程。
*   它根据到达时间填充就绪队列。
*   首先使用公式 Hp = 0.5 * Ep + 0.5 * R 执行最高混合优先级流程
*   重复步骤 4 和 5，直到队列变空。
*   现在，计算平均等待时间、平均周转时间、上下文切换次数。
*   它停止了。

#### 优势

*   这是非优先的。
*   它防止无限延期(饥饿过程)。
*   它提高了最短进程优先调度的性能。
*   它会考虑流程等待了多长时间，并提高其优先级。

#### 不足之处

*   进程的突发时间无法提前知道，因此无法实际实现。
*   进程由内部优先级系统调度，因为它不支持外部优先级系统。