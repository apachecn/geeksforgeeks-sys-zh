# VLAN 中继协议(VTP)

> 原文:[https://www.geeksforgeeks.org/vlan-trunking-protocol-vtp/](https://www.geeksforgeeks.org/vlan-trunking-protocol-vtp/)

要传送 VLAN 的流量，必须首先在交换机上进行配置。假设，如果用户想要从源向目的地发送一个帧，并且它们之间的最短路径包含 1000 个交换机。要处理任何 VLAN 帧，应首先配置虚拟局域网，因此必须在所有 1000 台交换机上手动配置相同的虚拟局域网。管理员不可能这样做。VTP 来救援了。

**VLAN 中继协议(VTP)–**
VTP 是思科专有协议，用于维护整个网络的一致性，或者用户可以说同步了同一 VTP 域中的 VLAN 信息。VTP 允许您添加、删除和重命名虚拟局域网，然后将其传播到 VTP 域中的其他交换机。VTP 广告可以通过 802.1Q 和 ISL 中继发送。

**要求–**
对 VTP 在交换机之间传递 VLAN 信息有一些要求。这些是:

1.  用户想要配置的交换机上的 VTP 版本必须相同
2.  交换机上的 VTP 域名必须相同
3.  其中一台交换机必须是服务器
4.  如果应用，身份验证应该匹配

**VTP 模式–**有 3 种模式:

1.  **Server –** The switches are set to this mode by default. This mode allows you to create, add and delete VLANs. The changes you want to made should be done in this mode. Any changes that is done on this mode(on a particular switch) will be advertised to all the switches that are in same VTP domain. In this mode, the configuration are saved in NVRAM.

    **配置–**用户将首先切换 VTP 服务器

    ```
    Switch# config terminal
    Switch(config)#vtp mode server
    ```

    现在，用户必须让 VTP 域分配一个密码进行身份验证。

    ```
    Switch(config)#vtp domain geeksforgeeks
    Switch(config)#vtp password hardwork
    ```

    用户可以通过以下方式验证配置:

    ```
    Switch(config)#do should vtp password 
    Switch(config)#do show vtp 
    ```

2.  **Client –** In this mode, the switches receives the updates and can also forward the updates to other switches(which are in same VTP domain). The updates received here is not saved in NVRAM so all the configuration will be deleted if the switch is reset or reloaded i.e the switches will only learn and pass the VTP summary advertisements to the other switches.

    **配置–**由于交换机默认设置为服务器模式，因此用户可以通过以下方式将其更改为客户端模式:

    ```
    Switch(config)#vtp mode client 
    ```

3.  **Transparent –** This mode only forwards the VTP summary advertisements through trunk link. The transparent mode switches can make their own local database which keep secret from other switches. The whole purpose of transparent mode is to forward the VTP summary advertisements but not to take part in the VLAN assignments.

    **配置–**用户可以通过以下方式将模式更改为透明

    ```
    Switch(config)#vtp mode transparent 
    ```

**配置修订号–**
配置修订号是一个 32 位数字，表示 VTP 数据包的修订级别。每个交换机都会跟踪该配置号，以便发现接收到的信息比当前版本更新。

每次服务器交换机对虚拟局域网进行一次修改，配置修订号就会增加一个。客户端模式设备接收它，并通过将其自身的配置号与接收到的号进行比较来检查它们接收到的配置修订号是否是最新的。如果配置号大于它们自己的配置号，则设备会更新它们的配置，并将其传递给同一 VTP 域的其他客户端。如果配置号相同，则设备会将其传递给同一 VTP 域的其他客户端。

用户可以通过以下方式检查配置修订号:

```
switch(config)#do show vtp status 
```