# 计算机网络中的端口安全

> 原文:[https://www . geesforgeks . org/port-计算机网络安全/](https://www.geeksforgeeks.org/port-security-in-computer-network/)

当攻击者能够进入他们想要攻击的网络时，他们的任务相对非常容易。以太网局域网很容易受到攻击，因为默认情况下，交换机端口是开放的。各种攻击，如第 2 层的 Dos 攻击、地址欺骗都可能发生。如果管理员可以控制网络，那么网络显然是安全的。要完全控制交换机端口，用户可以使用称为端口安全的功能。如果以某种方式阻止未经授权的用户使用这些端口，那么第 2 层的安全性将大大提高。

用户可以分两步保护端口:

1.  将媒体访问控制地址的数量限制在单个交换机端口，即如果超过限制，则从单个端口获知媒体访问控制地址，然后将采取适当的措施。
2.  如果观察到未经授权的访问，应该使用任何选项丢弃流量，或者更恰当地说，用户应该生成日志消息，以便可以轻松观察到未经授权的访问。

**端口安全–**
当帧通过交换机端口转发时，交换机会获知 MAC 地址。通过使用端口安全性，用户可以限制某个端口可以获知的媒体访问控制地址的数量，设置静态媒体访问控制地址，并在该端口被未经授权的用户使用时设置惩罚。用户可以使用限制、关闭或保护端口安全命令。

让我们讨论一下这些违规模式:

*   **protect–**此模式会丢弃源 mac 地址未知的数据包，直到您删除足够的安全 mac 地址，使其低于最大值。
*   **restrict–**此模式执行与保护相同的功能，即丢弃数据包，直到删除足够的安全 mac 地址，使其低于最大值。除此之外，它还将生成一条日志消息，增加计数器值，并发送 SNMP 陷阱。
*   **关闭–**与其他模式相比，该模式更受欢迎，因为如果进行了未经授权的访问，它会立即关闭端口。它还将生成一个日志，增加计数器值，并发送一个 SNMP 陷阱。该端口将保持关闭状态，直到管理员执行“不关闭”命令。
*   **粘性–**这不是违规模式。通过使用粘性命令，用户无需键入绝对的 Mac 地址即可提供静态 Mac 地址安全性。例如，如果用户提供的最大限制为 2，则在该端口上获知的前 2 个 Mac 地址将被置于运行配置中。在第二个获知的 Mac 地址之后，如果第三个用户想要访问，那么将根据应用的违规模式采取适当的措施。

**注意–**端口安全仅在接入端口上起作用，即要启用端口安全，用户首先必须将其设为接入端口。

**配置–**
在交换机的 fa0/1 接口上应用端口安全。首先，将端口转换为访问端口，并启用端口安全。

```
S1(config)#int fa0/1
S1(config-if)#switchport mode access
S1(config-if)#switchport port-security
```

使用粘性命令，这样它将动态学习 Mac 地址，并提供限制和应该采取的适当措施。

```
S1(config-if)#switchport port-security mac-address sticky
S1(config-if)#switchport port-security
maximum 2
S1(config-if)#switchport port-security violation shutdown
```

如果用户想要提供一个静态条目，那么通过启动它的 Mac 地址来配置它。

```
S1(config-if)#switchport port-security 
S1(config-if)#switchport port-security violation shutdown
S1(config-if)#switchport port-security mac-address aa.bb.cc.dd.ee.ff
```