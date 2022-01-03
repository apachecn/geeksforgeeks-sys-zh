# 思科交换机配置基本命令

> 原文:[https://www . geesforgeks . org/Cisco-switch-configuration-basic-commands/](https://www.geeksforgeeks.org/cisco-switch-configuration-basic-commands/)

**先决条件–**[开关功能](https://www.geeksforgeeks.org/switch-functions-at-layer-2/)

[交换机](https://www.geeksforgeeks.org/network-devices-hub-repeater-bridge-switch-router-gateways/)是第 2 层设备，用于将数据包从网络中的一台设备转发到另一台设备。它根据目的地媒体访问控制地址和媒体访问控制表中的条目，通过其中一个端口转发数据包。

以下基本命令用于配置新交换机:

**1。将交换机的主机名更改为 gfgsswitch:**

它用于设置设备的名称。

```
switch(config)#hostname GfgSwitch
GfgSwitch(config)#

```

**2。添加横幅消息:**

它向想要访问交换机的用户提供短消息。

```
GfgSwitch(config)#banner motd &
Enter Text message. End with character '&'
$ This is GeeksforGeeks floor Switch &

```

**3。要在交换机中设置 IP 地址:**

IP 地址是网络中设备的地址。

```
GfgSwitch(config)#interface vlan1
GfgSwitch(config-if)#ip address 172.16.10.1 255.255.255.0
GfgSwitch(config-if)#exit
GfgSwitch(config)#ip default-gateway 172.16.10.0

```

**4。设置当前时钟时间:**

这是设置存储在开关中的当前时间。

```
GfgSwitch#clock set 3:03:14 June 25 2020

```

**5。应用密码保护(启用密码、秘密密码、控制台密码和 vty 密码):**

*   **Enable password :**

    启用密码用于保护特权模式。

    ```
    GfgSwitch(config)#enable password GFGGFG

    ```

*   **启用秘密密码:**

    这也是用于保护特权模式，但不同的是在配置文件上会显示为密文(***)。

    ```
    GfgSwitch(config)#enable secret GFGGFG

    ```

*   **线路控制台密码:**

    当一个人通过控制台端口进行访问时，会询问该密码。

    ```
    GfgSwitch(config)#line console 0
    GfgSwitch(config-line)#password GFG
    GfgSwitch(config-line)#login

    ```

*   **线路 VTY 密码:**

    **当一个人想通过 VTY 线路(telnet 或 ssh)访问路由器时，就会询问这个密码。**

    ```
    GfgSwitch(config)#line VTY 0 2
    GfgSwitch(config-line)#password GFGGFG
    GfgSwitch(config-line)#exit 
    ```

****6。从运行配置文件复制到启动配置文件:****

```
GfgSwitch#copy running-config startup-config 
```

****7。观看启动配置文件和运行配置文件:****

```
GfgSwitch#show startup-config
GfgSwitch#show running-config 
```

****8。清除 mac 地址表:****

**交换机将媒体访问控制地址存储在媒体访问控制地址表中**

```
GfgSwitch#clear mac address-table 
```