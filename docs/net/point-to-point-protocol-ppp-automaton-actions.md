# 点对点协议自动机动作

> 原文:[https://www . geesforgeks . org/点对点协议-ppp-automaton-actions/](https://www.geeksforgeeks.org/point-to-point-protocol-ppp-automaton-actions/)

动作基本上是有限状态自动机的属性之一。当[点对点协议(PPP)](https://www.geeksforgeeks.org/ppp-full-form/) 连接从一种状态转换到另一种状态时，在自动化中会采取一些由一些事件引起的动作。行动通常是事件的结果，但不是每个事件都会导致行动的执行。这些行动如下:

1.  **非法-事件(-) :**
    非法事件，顾名思义，就是指不能发生的事件，由于某种错误而属于非法的事件，应该上报。
2.  **tlu :**
    这个动作标签的意思是“这一层往上”。这个动作只是向上层表明自动化正在简单地进入打开状态。该动作执行如下:

    ```
    if (f->callbacks->up)
    (*f->callbacks->up)(f); 
    ```

3.  **tld :**
    这个动作标签的意思是“这一层下来了”。这个动作只是向上层表明自动化只是离开开放状态。这一行动的实施如下:

```
if( f->callbacks->down )  
(*f->callbacks->down)(f);
```

*   **tls :**
    这个动作标签的意思是“这一层开始了”。此操作只是指示较低层，当自动化进入启动状态时，它们是连接或链接所必需的。此操作会获得高度依赖于实现的结果。该动作执行如下:

    ```
    if( f->callbacks->starting )
    (*f->callbacks->starting) (f);
    ```

    *   **tlf :**
    这个动作标签的意思是“这一层完了”。此操作只是指示较低层不再需要它们进行连接或链接，因为自动化正在进入初始、关闭或停止状态。此操作会获得高度依赖于实现的结果。该动作执行如下:

    ```
    if( f->callbacks->finished )
    (*f->callbacks->finished)(f);
    ```

    *   **irc :**
    这个动作标签的意思是“初始化重启计数”。重启计数器通常设置为正确的值，即最大终止或最大配置。对于每次传输，计数器递减，包括第一次传输。该动作执行如下:

    ```
    TIMEOUT(fsm_timeout, f, f->timeouttime);
    ```

    *   **zrc :**
    此动作标签表示“零重启计数”。作为此操作的结果，重启计数器通常设置为零。该动作执行如下:

    ```
    UNTIMEOUT(fsm_timeout, f);
    ```

    *   **scr :**
    该动作标签表示“发送配置请求”。此操作表明需要传输配置请求数据包，因此需要打开链接或连接以及一些指定的配置选项集。每当发送配置请求包时，重启定时器就会启动。这只是开始检查任何数据包丢失。该动作执行如下:

    ```
    fsm_sconfreq(f, 0) and
    fsm_sdata(f, CONFREQ, f->reqid, outp, cilen)
    ```

    *   **sca :**
    该动作标签表示“发送配置确认”。每当发送 configure-ack 数据包时，此操作都会确认收到 configure-request 数据包以及一组良好的配置选项。该动作执行如下:

    ```
    fsm_sdata(f, CONFACK, id, inp, len);
    ```

    *   **scn :** 此操作标签表示“发送配置 nak/rej”。每当发送配置-nak 或配置-拒绝数据包时，此操作都会确认收到配置-请求数据包以及一组错误的配置选项。该动作执行如下:

    ```
    fsm_sdata(f, CODEREJ, +>id, inpacket, len + HEADERLEN);
    ```

    *   **str :**
    该动作标签表示“发送终止请求”。这个动作表示需要发送终止请求分组，因此需要关闭链路或连接。每当发送配置请求包时，重启定时器就会启动。这只是开始检查任何数据包丢失。该动作执行如下:

    ```
    fsm_sdata(f, TERMREQ, f->reqid = +>id,  
    (u_char *) f->term_reason, f->term_reason_len);
    ```

    *   **sta :**
    该动作标签表示“发送终止确认”。每当发送终止-nak 包时，该动作确认终止-请求包的接收。该动作执行如下:

    ```
    fsm_sdata(f, TERMACK, id, NULL, 0);
    ```