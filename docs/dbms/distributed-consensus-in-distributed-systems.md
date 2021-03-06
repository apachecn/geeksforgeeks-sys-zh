# 分布式系统中的分布式共识

> 原文:[https://www . geesforgeks . org/distributed-consensus-in-distributed-system/](https://www.geeksforgeeks.org/distributed-consensus-in-distributed-systems/)

在分布式或分散式多代理平台中达成共同协议的过程。这对消息传递系统很重要。

**示例**–

网络中的许多进程决定选举一个领导者。每个过程都是从争夺领导权开始的。在传统或传统的分布式系统中，我们应用共识来确保可靠性和容错性。这意味着，在一个分散的环境中，当你有多个单独的方，并且他们可以自己做出决定时，那么可能会发生某些节点或某些方恶意工作或作为一个有缺陷的个人工作的情况。因此，在这些特殊情况下，做出决定或达成共同观点是很重要的。因此，在一个人们可以恶意行为或者人们可以以错误的方式破坏工作的环境中，有一个共同的观点是主要的困难。因此，在这种分布式环境下，我们的目标是确保可靠性，这意味着在有故障的个人存在时确保正确的操作。

**<u>特征:</u>**

*   它确保分布式系统的可靠性和容错性。
*   在有缺陷的个人存在的情况下，确保正确的操作。

**示例**–

提交数据库中的事务、状态机复制、时钟同步。

**如何达成分布式共识:**

为了达成分布式共识，需要遵循一些条件。

*   **终止–**
    每个无故障的流程最终都必须做出决定。
*   **协议–**
    每个无故障流程的最终决定必须相同。
*   **有效性–**
    每个无故障流程必须以相同的值开始和结束。
*   **正直–**
    每个正确的个体最多决定一个价值，决定的价值必须由某个个体提出。

这里有一个验证标准，所以基本上我们应该达成一个决定，这个决定的值必须是某个过程的初始值，因为当商定的值反映了没有人的初始选择时，达成一致是愚蠢的。

**分布式共识协议的正确性:**

它可以用以下两个属性来描述。

*   **安全属性–**
    它确保你永远不会收敛到不正确的值，或者网络中正确的个体永远不会收敛到不正确的值。
*   **Liveness Property–**
    它声明每个正确的值最终都必须被接受，这意味着美好的事情最终会发生。

**分布式共识的应用:**

*   容错环境中的领导者选举，在不引入单点故障的情况下启动一些全球行动。
*   在分布式网络中保持一致性。假设您有不同的节点监视同一个环境。如果其中一个节点崩溃，一个共识协议可以确保对这种故障的鲁棒性。