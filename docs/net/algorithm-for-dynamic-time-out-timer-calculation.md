# 动态超时计时器计算算法

> 原文:[https://www . geesforgeks . org/算法-用于动态超时-计时器-计算/](https://www.geeksforgeeks.org/algorithm-for-dynamic-time-out-timer-calculation/)

先决条件–[计算机网络| TCP 计时器](https://www.geeksforgeeks.org/computer-network-tcp-timers/)
计算**传输层超时计时器(TOT)** 很棘手，因为传播延迟不是恒定的，即路径可能会不断变化，流量是动态的。所以，静态 TOT 不能用在 TCP 上。并且不必要地多次重传相同的数据分组可能导致拥塞。
解决方案是我们需要动态 TOT，可以根据往返时间(RTT)的变化进行调整。

**动态 TOT 计算算法:**

1.  基本算法
2.  雅各布森算法
3.  Karn’s modification

    ### 1.基本算法–

    ```
    We assume initial round trip time i.e PRTT.
    On sending out each packet TOT = 2 * PRTT. 
    The next round trip time is calculated using
        PRTT<sub>n+1</sub> = α PRTT<sub>n</sub> + (1 - α)ARTT<sub>n</sub>
    where PRTT = predicted round trip time
          ARTT = actual round trip time
          α = smoothing factor such that 0<= α <=1 

    ```

    **例–**让 PRTT <sub>1</sub> = 10ms，α = 0.5

    ```
    TOT = 2 * PRTT1 = 20ms 
    Let ARTT1 = 15ms
    Then,
    PRTT2 = (0.5 * 10) + (0.5 * 15) = 12.5ms
    TOT = 2 * 12.5 = 25ms
    Let ARTT2 = 20ms
    PRTT3 = (0.5 * 12.5) + (0.5 * 20) = 16.25ms
    TOT = 2 * 16.25 = 32.5ms
    And so on TOT is calculated.

    ```

    **优势–**

    *   比静态 TOT 要好。
    *   TOT 对于动态往返时间是灵活的。
    *   它会考虑所有数据包来导出新的 PRTT。

    **缺点–**

    *   TOT = 2 * PRTT 用于为返回确认留出宽限期。
    *   这是浪费。

    ### 2.雅各布森算法–

    计算 TOT 值比基本算法更直观。

    ```
    We assume initial round trip time i.e. PRTT.
    PRTT<sub>n+1</sub> = α PRTT<sub>n</sub> + (1 - α)ARTT<sub>n</sub> 
    PD<sub>n+1</sub> = α PD<sub>n</sub> + (1 - α)AD<sub>n</sub> 
    where AD<sub>n</sub> = |PRTT<sub>n</sub> - ARTT<sub>n</sub>|
    AD = Actual deviation
    PD = predicted deviation
    On sending out each packet, TOT = (4 * PD) + PRTT. 

    ```

    **示例–**

    ```
    Iteration 1
    Given α = 0.5, PRTT1 = 10ms, PD1 = 5ms and ARTT1 = 20ms
    TOT = (4 * 5) + 10 = 30ms
    AD1 = |10 - 20| = 10ms

    Iteration 2
    PRTT2 = α PRTT1 + (1 - α)ARTT1
          = (0.5 * 10) + (0.5 * 20) = 15ms
    PD2 = α PD1 + (1 - α)AD1
          = (0.5 * 5) + (0.5 * 10) = 7.5ms
    TOT = (4 * 7.5) + 15 = 45ms
    Given ARTT2 = 30ms
    AD2 = |15 - 30| = 15ms

    Iteration 3
    PRTT3 = α PRTT2 + (1 - α)ARTT2
          = (0.5 * 15) + (0.5 * 30) = 22.5ms
    PD3 = α PD2 + (1 - α)AD2
          = (0.5 * 7.5) + (0.5 * 15) = 11.25ms
    TOT = (4 * 11.25) + 22.5 = 67.5ms
    Given ARTT3 = 10ms
    AD2 = |22.5 - 10| = 12.5ms
    And so on TOT is calculated.

    ```

    【Basic 和雅各布森算法的问题 T2【在两者中，**PRTT<sub>n+1</sub>=αPRTT<sub>n</sub>+(1–α)ARTT<sub>n</sub>**
    即两者都依赖于前一段 ARTT。但是如果初始超时定时器超时，那么将选择下一个 TOT，因为确认被延迟，即它在超时之后到来，所以 ARTT 不可用。

    ### 3.卡伦的修改–

    每当计时器超时时，不要应用基本或雅各布森算法，因为 ARTT 不可用，而是每当计时器超时并进行重传时，将超时计时器(TOT)加倍。

    [GATE | Gate IT 2007 |问题 13](https://www.geeksforgeeks.org/gate-gate-it-2007-question-13/)