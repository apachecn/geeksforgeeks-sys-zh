# 分布式系统中基于令牌和基于非令牌算法的区别

> 原文:[https://www . geesforgeks . org/分布式系统中基于令牌的算法和非基于令牌的算法的区别/](https://www.geeksforgeeks.org/difference-between-token-based-and-non-token-based-algorithms-in-distributed-system/)

一个[分布式系统](https://www.geeksforgeeks.org/design-issues-of-distributed-system/)是一个系统，其中的组件位于不同的地方，这些不同的地方指的是联网的计算机，它们可以通过互相交换消息来轻松地通信和协调它们的任务。这些组件可以相互通信，作为一项任务来征服一个共同的目标。

有许多算法被用来实现分布式计算，这些算法大致分为两类:基于令牌的算法和基于非令牌的算法。

**分布式系统中基于令牌和基于非令牌算法的区别:**

<center>

| 没有。 | 基于令牌的算法 | 基于非令牌的算法 |
| 1. | 在基于令牌的算法中，分布式计算系统中的所有站点共享唯一的令牌。 | 在基于非令牌的算法中，没有令牌，甚至没有共享令牌进行访问的概念。 |
| 2. | 在这里，如果一个站点拥有令牌，它就可以进入计算机系统。 | 在这里，两个或多个连续的消息在站点之间交换，以确定下一个进入计算机系统的站点。 |
| 3. | 基于令牌的算法使用这些序列对计算机系统的请求进行排序，并解决对系统的同时请求的冲突。 | 基于非令牌的算法使用时间戳(另一个概念)对计算机系统的请求进行排序，并解决对系统的同时请求的冲突。 |
| 4. | 与基于非令牌的算法相比，基于令牌的算法产生的消息流量更少。 | 与基于令牌的算法相比，基于非令牌的算法产生更多的消息流量。 |
| 5. | 由于分布式系统中唯一令牌的存在，它们没有死锁(也就是说，队列中没有两个或更多的进程来等待实际上不能到来的消息)。 | 它们不能避免死锁问题，因为它们只基于时间戳。 |
| 6. | 这里，确保了请求完全按照发出的顺序执行。 | 这里没有执行令的保证。 |
| 7. | 基于令牌的算法更具可扩展性，因为它们可以让您的服务器不必存储会话状态，而且它们包含了认证所需的所有必要信息。 | 基于非令牌的算法比基于令牌的算法扩展性差，因为在这里服务器不能摆脱它的任务。 |
| 8. | 这里的访问控制非常细粒度，因为在这里，可以很容易地为用户指定令牌角色、权限和资源。 | 这里的访问控制没有那么好，因为没有可以为用户指定角色、权限和资源的令牌。 |
| 9. | 基于令牌的算法使身份验证变得非常容易。 | 基于非令牌的算法无法简化身份验证。 |
| 10. | 基于令牌的算法的例子有:

```
(i) Singhal’s Heuristic Algorithm
(ii) Raymonds Tree Based Algorithm
(iii) Suzuki-Kasami Algorithm    
```

 | 基于非令牌的算法的例子有:

```
(i) Lamport’s Algorithm
(ii) Ricart-Agarwala Algorithm
(iii) Maekawa’s Algorithm 
```

 |

</center>