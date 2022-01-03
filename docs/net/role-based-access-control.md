# 基于角色的访问控制

> 原文:[https://www.geeksforgeeks.org/role-based-access-control/](https://www.geeksforgeeks.org/role-based-access-control/)

只有管理员才能完全访问网络，而像初级网络工程师这样的其他员工不需要完全访问网络设备。初级工程师通常只需要交叉检查设备的配置，而不需要添加或删除任何配置，那么为什么要给予该员工完全的访问权限呢？
对于这些类型的场景，管理员根据用户的角色定义对设备的访问。

**基于角色的访问控制–**
基于角色的访问控制的概念是创建一组权限，并将这些权限分配给用户或组。在这些权限的帮助下，只能向用户提供有限的访问权限，从而提高了安全性。
有不同的方式执行 RBAC，如创建自定义权限级别或创建视图。

**自定义级特权–**
当我们拿起路由器的控制台时，我们进入用户级模式。用户级模式的权限级别为 1。通过键入 enable，我们进入特权模式，其中特权级别为 15。拥有 15 级权限的用户可以访问 15 级或以下的所有命令。
通过创建自定义权限级别(介于 2 和 14 之间)并为其分配命令，管理员可以向用户提供命令子集。

**配置–**
首先，我们将向我们的权限级别添加一个命令，比如 8，并为其分配一个密码。

```
R1(config)#privilege exec level 8 configure terminal
R1(config)#enable secret level 8 0 saurabh
```

在这里，我们将密码指定为 saurabh。还要注意，这里的 0 表示后面的密码是明文(非哈希)。
现在，我们将创建一个本地用户名 saurabh，并将该用户与配置的级别相关联。启用 aaa 模型并将默认列表分配给不同的行。

```
R1(config)#username saurabh privilege 8 secret cisco123
```

```
R1(config)#aaa new-model
R1(config)#line vty 0 4
R1(config)#login local
```

现在，每当用户名 Saurabh 通过 vty 线路进行远程访问时，他将被分配 8 级权限。

**创建视图:**
基于角色的 CLI 访问使管理员能够为不同用户创建设备的不同视图。每个视图定义了用户可以访问的命令。它类似于特权级别。基于角色的命令行界面提供两种类型的视图:

1.  **Root view –** Root view has the same access privilege level as user who has level 15.The administrator should be in root view as view can be added, edited or deleted in root view.

    **Configuration –**
    To enter into root view, we first have to enable aaa on the device and then have to set enable password or secret password which will be used when any user will enter the root view.

    To enable aaa on the device and to apply secret password, command is:

    ```
    R1(config)#aaa new-model
    R1(config)#enable secret geeksforgeeks
    ```

    现在，我们将通过命令进入根视图:

    ```
    R1#enable view
    ```

    通过键入这个，我们将进入根级别，在那里我们可以添加、删除或编辑视图。

2.  **Super view –** A super view consists of 2 or more CLI views. A network administrator can assign a user or group of users a superview which consists of multiple views. A super view can consists of more than one view therefore it has the access to all the commands which are being provided in other views.

    **Configuration –**
    As the super view consists of more than one view therefore first we will create 2 views named, Cisco and IBM. Now, in view Cisco, we will allow all show command in exec mode and int e0/0 command on global configuration mode.

    ```
    R1(config)#parser view cisco
    R1(config-view)#secret geeksforgeeks1
    R1(config-view)#commands exec include all show
    R1(config-view)#commands configure include int e0/0
    ```

    现在，我们将创建 IBM 视图，其中我们将允许在执行模式下 ping 和配置终端，在配置模式下配置 ip 地址。

    ```
    R1(config)#parser View ibm
    R1(config-view)#secret geeksforgeeks1
    R1(config-view)#commands exec include ping
    R1(config-view)#commands exec include config terminal
    R1(config-view)#commands configure include ip address 
    ```

    现在我们将创建一个超级视图，并将其命名为 sup_user。我们将为 superview sup 用户启用一个秘密密码超级用户，并向其添加思科和 IBM 视图，因此它拥有执行仅包含在思科和 IBM 视图中的命令的所有权限。

    ```
    R1(config)#parser view sup_user superuser
    R1(config-view)#secret superuser
    R1(config-view)#view cisco
    R1(config-view)#view ibm
    ```

**注意–**在配置任何视图之前，都需要对其应用密码。此外，这里可以使用使能密码，而不是秘密密码，但它不太安全，因为它没有加密。
我们可以通过以下方式检查配置:

```
R1#show running-configuration
```