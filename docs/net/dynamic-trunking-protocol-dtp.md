# 动态中继协议(DTP)

> 原文:[https://www . geesforgeks . org/dynamic-trunking-protocol-DTP/](https://www.geeksforgeeks.org/dynamic-trunking-protocol-dtp/)

中继端口是用于承载多个 VLAN 流量的端口。连接两个不同交换机的端口，并且交换机配置了多个 VLAN，则该端口应成为中继端口。如果所有的虚拟局域网都被允许，那么中继端口将承载所有虚拟局域网的流量，包括流量未被标记的本地虚拟局域网，否则只有被允许的虚拟局域网流量将由中继链路承载。中继链路流量将由交换机间链路或 802.1Q 封装或标记

默认情况下，所有交换机端口都是接入端口，因此要建立端口中继，用户应该使用 DTP 手动建立中继。

**动态中继协议–**
动态中继协议是 CISCO 专有协议，用于协商两台交换机之间的中继链路以及 802.1q 或 ISL 的封装类型(通常使用 802.1q，因为 ISL 的开销比 802.1q 大)。当然，它是第 2 层(数据链路)协议，默认情况下是启用的。

以下是配置交换机接口时可用的不同选项

**交换机端口模式接入(DTP 模式关闭)–**
该模式将交换机接口置于永久非中继模式，无论相邻接口是中继端口还是试图成为中继端口，这就是为什么它被称为 DTP 模式关闭。该端口是专用的第 2 层接入端口。

**交换机端口模式中继(DTP 模式开启)–**
它将接口置于中继模式。该接口将成为中继接口，即使相邻端口是否是中继，这就是为什么它被称为 DTP 模式开。

**交换机端口模式动态自动–**
这是旧思科交换机的默认模式。这种模式使接口能够转换为中继链路。如果相邻接口设置为中继或理想模式，该接口将成为中继链路。如果两个交换机的接口模式都是自动的，则不会形成中继。

**交换机端口模式动态可取–**
通过该模式，接口将主动尝试将链路转换为中继链路。如果相邻接口设置为中继、理想或自动，该接口将成为中继端口。

**交换机端口非协商–**
此模式阻止接口生成 DTP 帧。此命令仅在交换机端口模式为接入或中继时使用。您必须手动将相邻接口配置为中继接口，以建立中继链路。

现在，让我们看看交换机接口将成为中继或接入接口的场景。

<figure class="table">

|   | **动态自动**
 | **动感可取**T2】 | **干线**T2】 | **访问**
 |
| 动态自动 | 接近 | 树干 | 树干 | 接近 |
| 动态理想 | 树干 | 树干 | 树干 | 接近 |
| 树干 | 树干 | 树干 | 树干 | 有限的连通性 |
| 接近 | 接近 | 接近 | 有限的连通性 | 接近 |

通过观察这一点，很明显，每当您收到请求形成中继的 DTP 数据包时，您的接口将处于中继模式。

</figure>