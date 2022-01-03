# 概率计算介绍

> 原文:[https://www . geesforgeks . org/概率计算导论/](https://www.geeksforgeeks.org/introduction-of-probabilistic-computing/)

近年来，在商业、科学或互联网中收集的信息量呈爆炸式增长，人们越来越多地要求计算机帮助人们解释所有这些数据并根据这些数据采取行动。

**比如**，当地的温度数据告诉了我们什么是全球气候系统，网上冲浪和购物告诉了我们什么是消费者，基因数据如何用于个性化医疗。

这些可识别的问题看起来各不相同，但实际上是相似的。它们都需要归纳推理，从对世界的观察中归纳出它们的根本原因。我们用的电脑不是为它设计的，也不擅长它。**为什么？**

计算机最初是为了解决科学和技术问题而设计的，但我们很快就开始将其用于商业需求。自从它的到来，计算机也变成了通讯和娱乐设备。**但是当计算机被要求理解数据时会发生什么？**

计算机可以被认为是执行一组指令的机器，这些指令告诉它如何将输入转换成输出。用计算机解释或理解数据有两种方式- **模拟和推理。**

在**模拟**中，机器以一些背景假设作为世界的输入配置开始，并产生一个观察到的轨迹作为输出。这很容易，因为机器执行指令的方向与建模过程从原因到影响的方向相同。

**推断**是逆向问题。机器从相同的背景假设开始，但把观察到的轨迹作为输入，并把解释它的世界结构作为输出。在这里，机器必须从事实回到它们可能的原因。对数据进行推论的一个常见挑战是，对于特定的输出，通常有许多可能的解释。换句话说，关于哪个解释是正确的，存在根本的不确定性。当解释和解释数据时，这种不确定性是一个基本问题。它是如此的普遍，以至于我们不能期待关于数据的绝对确定的答案，但是我们可以做出包含尽可能多的知识的好的猜测。

好的猜测平衡了与背景知识的一致性和与数据的契合度，不会引入不必要的复杂性。在传统计算中，推理指令比模拟指令更难编写，因为我们通常从一件事如何导致另一件事的角度收集科学行为和技术知识的代码。因此，在这个方向上利用知识要比在相反的方向上容易得多。但是，这些逆向或推理应用通常对商业和社会都更有价值。

概率计算机自动将模拟指令转换成推理程序，并管理偶然解释的不确定性。这些机器是为翻译而设计的。