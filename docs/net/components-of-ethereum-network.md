# 以太网组件

> 原文:[https://www . geesforgeks . org/components-of-ether eum-network/](https://www.geeksforgeeks.org/components-of-ethereum-network/)

在本文中，我们将讨论 Ethereum 网络的概述，并讨论其优势，最后以 [Ethereum](https://www.geeksforgeeks.org/introduction-to-ethereum-part-1/) 网络的组件结束。我们一个一个来讨论。

**概述:**

*   程序员 Vitalik Buterin 在 2013 年提出了 Ethereum。该网络在 2014 年众筹后，于 2015 年上线，最初供应 7200 万枚硬币。
*   以太网虚拟机(EVM)可以运行分散的程序和执行脚本。Ethereum 用于分散银行业务、不可替代代币的生产和分销以及许多 ico。
*   继比特币之后，以太币被称为第二大流行的加密货币。与比特币不同，以太琴被认为不仅仅是一种交换手段或价值储存手段。
*   另一方面，Ethereum 将自己称为基于区块链技术的分散式计算机网络。以太博物馆建立在区块链网络之上。区块链是一个透明、分布式的公共分类账，用于核实和记录所有交易。Ethereum 网络上的每个人都有这个分类账的精确副本，这允许他们查看所有以前的交易。
*   以太网网络允许用户构建和运行应用程序、智能合约和其他交易。这些功能在比特币中不可用。
*   它只是作为交换的媒介和现金的储存。以太代币可以生产多少没有边界，而比特币只能交付 2100 万枚硬币。
*   多亏了 Ethereum，所有人，无论背景或位置，都可以获得数字货币和数据友好的资源。正是这项技术为以太网(ETH)和当今成千上万的其他应用提供了动力。
*   以太网虚拟机(EVM)由以太网客户端运行，可以用任何流行的编程语言构建。

**etherneum 客户端实现的好处:**
拥有如此多的 etherneum 客户端实现有几个好处，包括以下几点。

1.  它增强了网络的抗 bug 能力。
2.  它防止开发资源集中。
3.  一般来说，团队竞赛有助于发现常见和困难问题的最佳解决方案。
4.  在采矿、原型制作、DApp 开发和其他领域，每个客户可能都有独特的侧重点、优势和劣势。DApp 开发商和私人以太博物馆区块链运营商可能会挑选最适合他们的目的。

**以太网组件:**

**组件-1 :**
**节点–**
以太网网络中有两种类型的节点。它们如下。

1.  **挖掘节点–**
    这些节点负责写入块中以太网网络中发生的所有事务。

2.  **Ethereum 虚拟机节点–**
    这些是 Ethereum 网络中的节点，在这些节点中，智能合约(它是支持者和开发者之间的一种合约，其中有一组规则，基于这些规则，双方同意相互交互。当满足预定义的规则时，协议将自动执行。)都实现了。默认情况下，该节点使用 30303 端口号进行相互通信。

**组件-2 :**
**以太–**

*   以太是一种用于以太网的加密货币，就像比特币用于区块链网络一样。它是一种点对点货币，类似于比特币。它跟踪和促进网络中的每个交易。
*   它是世界上第二大加密货币。第一个是比特币。其他加密货币可以用来获得以太代币，但反之则不然。
*   这意味着以太代币不能被其他加密货币互换，从而为以太交易提供计算能力。以太作为一种佣金支付给任何影响以太博物馆状态的处决。
*   在以太网算法中，它被用来激励使用工作证明方法将区块连接到区块链的矿工。
*   这是唯一可以用来支付交易成本的货币，交易成本也归矿工所有。大宗奖励以及交易费为矿商提供了一个保持区块链上涨的机会。
*   除了支付交易费用之外，以太网还经常被用来购买天然气，天然气被用来支付以太网上任何交易的计算费用。

**成分-3 :**
**气体–**

*   天然气是以太网的内部货币。我们需要天然气来运行以太网网络上的应用程序，就像我们需要天然气来运行车辆一样。
*   为了完成以太网网络上的每一笔交易，消费者必须首先进行支付——发送以太——中间货币价值被称为气体。
*   Gas 是 Ethereum 网络上用于执行智能合同或交易的计算能力的度量单位。
*   与乙醚相比，天然气的价格很低。执行和资源利用成本在 Ethereum 中以气体单位预先确定，称为 **gwei。**

**组件-4 :**
**以太坊账号–**
以太坊账号有两种类型。它们如下。

1.  **外部拥有账户–**
    这些账户用于存储交易。

2.  **合约账户–**
    顾名思义，这些账户存储智能合约的详细信息。

**Component-5:**
**Nonce–**
对于外部拥有的账户，Nonce 表示通过该账户的交易数量。对于合同账户，nonce 指通过该账户生成的合同数量。

**成分-6 :**
**贮藏根–**
它是一棵 Merkle 树的主根节点。账户的所有详细信息都存储在这里。Merkle 树的根是所有事务的验证。

**组件-7:**
**Ethash–**
ether eum 1.0 的预定 PoW 算法是 Ethash。这是匕首桥本的最新版本，然而，称之为匕首桥本不再合适，因为许多算法的初始特征在研究和开发的前一个月已经发生了巨大的变化。原始版本可以在这里找到。

**算法:**
算法遵循如下一般路径如下。

1.  每个块都有一个种子，可以通过读取块头直到那个点来确定。
2.  可以从种子计算出 16 MB 的伪随机高速缓存。缓存由轻型客户端保存。
3.  我们可以从缓存中构建一个 1 GB 的数据集，条件是数据集中的每个项目只依赖于几个缓存项目。数据集由完整客户端和挖掘器存储。数据集随时间线性扩展。
4.  获取数据集的随机切片并将它们散列在一起就是挖掘的全部内容。通过利用缓存更新数据集中您需要的部分，只需要存储缓存，就可以用很少的内存完成验证。