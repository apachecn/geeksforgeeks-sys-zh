# 破解密码

> 原文:[https://www.geeksforgeeks.org/breaking-cryptography/](https://www.geeksforgeeks.org/breaking-cryptography/)

在本文中，我们将讨论[对称加密](https://www.geeksforgeeks.org/symmetric-encryption-cryptography-in-java/)协议的概述以及[非对称加密](https://www.geeksforgeeks.org/asymmetric-encryption-cryptography-in-java/)的必要性进入了画面，在这里我们将讨论概述、密码学示例以及破解密码学的规则？我们一个一个来讨论。

**概述:**
一个密钥对消息进行加密，这个密钥可以解密消息。然后，一旦爱丽丝和鲍勃就密钥达成一致，他们就可以交换消息。但是他们怎么能在被窃听者监控的网络上就一个秘密密钥达成一致呢？让我们假设窃听者是屋檐！现在，为了解决这个问题，我们改用非对称密钥。

**示例–**

*   爱丽丝用鲍勃的公钥加密她的消息，因为只有鲍勃才能用他自己的私钥解密消息。同样，鲍勃加密
*   他的带有爱丽丝公钥的消息只能用爱丽丝的私钥解密。
*   现在，爱丽丝也可以使用这种方法向鲍勃认证自己。
*   她可以用她的私钥加密她的消息，然后用鲍勃的公钥加密结果。当鲍勃用他的
*   自己的私钥，他看到已经存在一个加密的内层。现在，如果这可以用爱丽丝的公钥加密，那么他就会
*   确定是爱丽丝加密的。

**生成一个私钥:**
现在让我们进入这些密钥最初是如何生成的本质，如下所示。

**进场–**

1.  生成私钥在计算上非常困难。它根本不能通过逆向工程由一种称为 RSA 算法的算法产生的公钥来产生。
2.  RSA 算法的协议是什么？
3.  我们产生一个数(N)，它是两个质数(比如 p 和 q)的乘积
4.  现在，产生的数字相当大(接近几百到一千位数)。

```
p ∗q = N
```

**例–**
我们用一个简单的例子来理解，如下。

**步骤-1 :**
通过使用上述协议，让我们使用两个素数的乘法来定义 n。(直接取质数会使计算变得复杂。)

```
p=61, q =53.
compute N.  
N = p*q
N = 3233
Applying Euler's Totient function,  
∅(n) = ∅(p*q)
     = ∅(p) * ∅(q)
     = (p-1)*(q-1)
     = 60*52
     = 3120
```

**第二步:**
我们没有直接取 N，因为我们要计算一系列与之同素的数字会变得很复杂。

```
Choose 'e' ; 1<=e<= ∅(n), co prime to  ∅(n)
Going by that, if we take e = 17
Then,  Gcd(17,3120) should be = 1 
(that means the numbers should be co-prime to each other.)

our public key is :(e,N)= (17,3233)
```

**第三步:**
现在我们来确定私钥:(d，N)

```
e d = 1 mod ∅(n)
here e and ∅(n) are co primes to each other
Now going by the concept of Multiplicative Inverse we have,
d =  e-1 mod ∅(n)
Finding d:
d is calculated using the formula:
= [(∅(n) * i)+1]/e
```

**Step-4 :**
我们继续通过改变 I 的值来计算，这里我们取 I 为 1，2，3…，等等。直到我们得到一个非十进制数的答案。

```
at i = 15, we get d as 2753
hence our private key becomes:
(d,N)=(2753,3233)
```

**步骤-5 :**
生成公钥和私钥后，我们执行加密和解密。

```
(m e)d ≡ m mod N, 
 where 
 m - It is the message. Such computation is a one way function.
```

RSA 算法的优势在于 N。数字 N 越大，它取出质因数的速度就越慢。

**破解密码学:**
讨论完这个，让我们进入如何破解密码学！

1.  如果我们知道如何计算巨大的数字，破解开放的安全系统将会很容易。
2.  RSA 使用这些主要因素作为密钥来解密这些消息。为此，我们需要找出一个巨大数字的质因数！
3.  现在，这可能会变得非常无聊和耗时。
4.  我们需要一个战略计划来考虑这些因素。著名数学家欧拉前来救场。他仔细考虑了质数和
5.  它给出了各种假设，比如模运算。基本上，他给出了 RSA 密码系统下的所有数学。
6.  模块化算法:
7.  这里我们考虑两个数相除时的余数。

```
a ≡ x mod N
when we divide a/N, the remainder is --> x
2 × 3 = 6
6/5 = 1
so,  
2 × 3 mod 5 is 1
its written as:
2*3 ≡ 1 mod 5
```

**求幂与模运算的关系:**
下面我们来看看求幂与模运算的关系。

让我们借助例子来理解。

1.  如果我们取 3 (3 <sup>k</sup> 的幂，我们将得到 3，9.27，81，243
2.  现在，如果我们取 10 个数的模，我们得到一个序列，如 9，7，1，3，9，7，1，3…等等。
3.  我们观察到，幂的顺序增加了，但是模周期重复了。
4.  我们还观察到模式的最后一位总是 1。
5.  现在，只要 x 和 N 是 co 素数，x mod N，x <sup>2</sup> mod N，x <sup>3</sup> mod N …所有这些都会持有这个属性。
6.  我们称之为重复模式周期的长度。
7.  这里，3 mod 10 的周期是 4(因为在每四个数字之后，模式重复)
8.  周期是最小的数字“r”，这样，

```
x r ≡ 1 mod N
```

**计算一个数的因子:**
现在我们来看看模运算、求幂和周期是如何与计算这个数的因子相关联的。

假设给你一个数字 N，你也给了它的因子 p 和 q，关于 p 和 q 什么都不知道。

```
N = p .q
```

**第一步:**
拿起任何小于 n 的数字，我们称之为‘a’。检查 a 和 N 是否为 co 素数。我们通过两者的 GCD 来检查这一点。GCD(a，N)=1，则它们互为素数。

**Step-2 :**
第二步是计算一个 mod N 的周期，在这个例子中，我们取 N = 32，假设 a = 8(因为它们都是同素的。)让我们假设周期为“r”。

```
powers of 8 = 8,64,512,4096.....
mod 35 = 8,29,22,..1
We compute r to be as 4.
```

为了进行算术运算，我们需要将 r 除以 2。所以，我们需要知道 r 是偶数。稍后，我们还需要知道 a <sup>r/2</sup> + 1 ≇ 0 mod N。如果这两者都失败了，我们需要在开始步骤中选择一个不同的“a”。

**第三步:**
对于第三步，我们要做一些代数如下。让我们从我们知道的事情开始。

```
ar ≡ 1 mod N
which on subtracting 1, gives  
ar  - 1 ≡ 0 mod N
```

如上所述，相当于说它是 N 的倍数(因为这里得到的余数是 0。)所以，一定存在一些整数‘k’，比如:

```
ar - 1  = k .N
Since we assumed 'r' as an even number here, we can write it as : 
(a r/2 - 1 )(a r/2 +1 )= k. N

Since N=p .q, so we replace N with  p . q
(a r/2 - 1 ) (a r/2 +1 ) = k. p .q

Since, we have the period of 8 mod 35 as 4, we can write it as:
84 ≡ 1 mod 35

so, 84 - 1 ≡ 0 mod 35 (its equivalent to saying that its a multiple of N)
So we can re write it as: 84 - 1 = k . 35
rewriting this as (since r is even here):

(8r/2 - 1)(8r/2 + 1) = k. p .q (where p .q are the prime factors of N)
```

**Step-4 :**
现在，step 4 是计算 p & q，这里我们假设 GCD((a<sup>r/2</sup>–1)，N)是质因数之一。姑且称之为 p .并且，GCD((a <sup>r/2</sup> + 1)，N)是另一个质因数。我们称之为 q，在等式(a<sup>r/2</sup>–1)(a<sup>r/2</sup>+1)= k . p . q 中，我们假设 p 必须除左侧的一个因子，q 也必须除左侧的一个因子。他们两个不能在左边划分相同的因子，因为那个因子可以被 n 整除

**肖尔算法:**
我们做如下假设。

```
p divides (ar/2 - 1) and q divides (ar/2 + 1)
We get, p = Gcd(63,35) = 7
and q is the Gcd(65,35) = 5
```

让我们快速回顾一下我们的工作，如下所示。

1.  取小于 n 的 a。
2.  求模 N 的周期
3.  用代数重新排列
4.  设 p = Gcd((a<sup>r/2</sup>–1)，N)和 q = Gcd ((a <sup>r/2</sup> + 1)，N)

你完蛋了！你破坏了安全系统。但我们知道，RSA 仍然有效，去掉周期需要很长时间。但是，量子计算机的作用来了。他们擅长计算周期。以上是绍尔算法的概要。