# 权威共识证明

> 原文:[https://www.geeksforgeeks.org/proof-of-authority-consensus/](https://www.geeksforgeeks.org/proof-of-authority-consensus/)

在[区块链](https://www.geeksforgeeks.org/blockchain-technology-introduction/)平台中，共识机制可以分为无许可(如以太网、[比特币](https://www.geeksforgeeks.org/what-is-bitcoin/))和许可(如 [Hyperledger](https://www.geeksforgeeks.org/introduction-of-hyperledger/) 、以太网 Private)。与任何人都可以成为节点的无权限区块链不同，在有权限的区块链，所有节点都是预先选择的。这允许使用具有高可伸缩性和高带宽的共识类型。其中一种共识类型是**权威证明(PoA)共识**，它提供了高性能和容错能力。术语是由 Ethereum 和平价技术公司 Gavin Wood 的联合创始人在 2017 年提出的。

**PoA 的工作:**

*   在 PoA 中，生成新块的权利被授予已证明其权限的节点。这些节点被称为**“验证器”**，它们运行允许它们将事务分块的软件。该过程是自动化的，不需要验证者不断地监控他们的计算机，但确实需要保持计算机不受损害。POA 既适用于私有网络，也适用于公共网络，就像 PoA 网络一样，信任是分布式的。
*   PoA 共识算法利用了身份的价值，这意味着区块验证者不是在下注硬币，而是他们自己的声誉。PoA 通过对所选身份的信任来保护。

**PoA 共识和常见攻击:**

1.  **[分布式拒绝服务攻击(DDos)](https://www.geeksforgeeks.org/denial-of-service-ddos-attack/) :**
    分布式拒绝服务(DDos)攻击是一种试图通过让来自多个来源的流量淹没在线服务来使其不可用的攻击。攻击者向目标网络节点发送大量事务和块，试图中断其操作并使其不可用。

PoA 机制使得防御这种攻击成为可能，因为网络节点是经过预认证的，块生成权限只能授予能够抵御 DoS 攻击的节点。

*   **51% attack :**
    In PoA consensus, 51% attack requires an attacker to obtain control over 51% of network nodes. This is different from 51% attack for the Proof-of-Work consensus types where an attacker needs to obtain 51% of network computational power. Obtaining control of the nodes in permissioned blockchain network is much harder than obtaining computational power.

    通过活动方案，个人获得了成为验证者的权利，因此有动力保留他们获得的职位。验证者受到声誉的激励，声誉让他们保留自己作为节点的权威。PoA 只允许来自任何一个验证器的非连续块批准，这意味着严重损坏的风险被集中到权限节点。

    **PoA 共识的条件:**

    *   活动方案共识可能因实施方式不同而有所不同，但通常通过以下条件适用:
    *   验证者需要确认他们的真实身份。
    *   一个候选人必须愿意投资金钱，并把自己的声誉置于危险之中。艰难的过程降低了选择有问题的验证者的风险，并激励了对区块链的长期承诺。
    *   选择验证器的方法必须等于所有候选项。
    *   必须验证验证者的身份，以保持区块链的完整性。某种过程应该是他们选择诚实的验证者。

    **PoA 共识的优势:**

    *   风险容忍度高，只要 51%的节点没有恶意行为。
    *   生成新块的时间间隔是可预测的。对于 PoW 和 PoS 共识，这一时间有所不同。
    *   交易率高。
    *   比像工作证明这样需要计算能力的算法更可持续。

    **限制:**

    *   PoA 不是去中心化的，而只是努力让中心化的系统更有效率。
    *   PoA 验证器对任何人都是可见的。了解验证者的身份可能会导致第三方操纵。

    **活动方案共识的应用:**

    *   PoA 共识算法可应用于各种场景，被认为是供应链等物流应用的绝佳选择。
    *   权威证明模式使公司能够在利用区块链技术优势的同时保护自己的隐私。微软 Azure 是另一个正在实施 PoA 的例子。Azure 平台为私有网络提供解决方案，其系统不需要像 Ethereum 上的 ether 'gas '这样的本地货币，因为不需要挖掘。Azure 节点是预先选择的。