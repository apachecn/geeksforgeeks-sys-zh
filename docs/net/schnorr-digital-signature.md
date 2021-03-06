# 施诺尔数字签名

> 原文:[https://www.geeksforgeeks.org/schnorr-digital-signature/](https://www.geeksforgeeks.org/schnorr-digital-signature/)

在[密码学](https://www.geeksforgeeks.org/cryptography-and-its-types/)中，**施诺尔签名**是由克劳斯·施诺尔描述的施诺尔签名算法产生的数字签名。它是一种以简单、高效和生成短签名而闻名的数字签名方案。它是用于实现“知识证明”的协议之一。在密码学中，知识证明是一种交互式证明，在这种证明中，证明者成功地“说服”验证者，证明者知道某个“X”。为了让机器知道“X”是根据计算定义的。如果这个“X”可以计算，机器就知道“X”。验证者接受或拒绝证明。签名证明应该使验证者相信他们正在与知道与公钥对应的私钥的用户通信。换句话说，验证者应该确信他们在不知道私钥的情况下与证明者通信。

**施诺尔数字签名实现[零知识证明](https://www.geeksforgeeks.org/zero-knowledge-proof/) :**
我们以两个朋友萨钦和三奇塔为例。桑奇塔已经向全世界宣布，她有一把公钥，可以通过它接受和接收信息。萨钦认为桑奇塔在撒谎。桑奇塔想在不出示私人钥匙的情况下证明自己的诚实。这就是施诺尔的方案能帮助我们的地方。

```
Consider the following parameters: 
p, q, a, s, v, r, x, y

where,
"p" is any prime number
"q" is factor of p-1
“a” such that a^q = 1 mod p 
```

以上三个变量是全局和公共的，这意味着任何人都可以在给定的场景中看到这三个变量。

我们会有两把钥匙。

```
"s" is the secret key or the private key (0<s<q).
"v" is the public key = a^-s mod q. 
```

公钥“v”以及 p、q 和 a 将是全局和公共知识。然而，只有桑奇塔知道私钥“s”。

现在桑奇塔签想发送一条加密信息“M”。她将按照以下步骤使用施诺尔的签名:-

1.  她将首先选择随机数“r ”,使得 0
2.  她现在将计算一个值 x，这样:X= a^r 模 p。
3.  现在，她已经计算了 X 的值，她将把它与原始消息连接起来(与字符串连接相同)。
    因此，她将连接 M 和 X 以获得 M||X。她将把这个值的散列存储在 e.

    ```
    e = H(M||X) where H() is the hash function 
    ```

    中
4.  她将得到一个值“y”，比如:

    ```
    y = (r + s*e) mod q 
    ```

现在所有的计算都结束了，她打算把以下内容发给萨钦。

1.  信息
2.  签名 e 和 y。

除此之外，萨钦还有以下公开信息

1.  桑奇塔的公钥“v”。
2.  桑奇塔选择“p”的质数。
3.  “q”，这是桑奇塔选择“p-1”的因素。
4.  “a”表示 a^q = 1 mod p，由桑奇塔选择。

现在，萨钦将不得不这样计算 X:

```
X’ = a^y * v^e mod p 
```

我们知道 v = a^-s，让我们把它代入上面的等式，我们得到:

```
X’ = a^y * a^-se = a ^ (y-s*e) 
```

现在我们也知道，

```
y = r + s*e

Which means: 
r = y-s*e 
```

让我们在上面的等式中替换这个值:

```
We get: X’ = a^r 
```

正如我们在上面已经看到的:

```
X= a^r 
```

所以技术上来说:

```
X = X’ 
```

但是萨钦不知道“X”的价值，因为他从来没有得到过那个价值。他收到的所有信息如下:消息 M、签名(e 和 y)和公共变量(公钥“v”、p、q 和 a)的宿主。

因此，他将通过执行以下操作来求解 e:

```
e = H ( M||X’) 
```

请注意，之前我们求解 e 的方法是:

```
H(M||X)) 
```

所以，按照这个逻辑，如果 e 的两个值相同，那就意味着

```
X = X’ 
```

这遵循零知识证明的所有三个属性:

1.  **完整性–**
    萨钦对桑奇塔的诚实深信不疑，因为最终 X = X’。
2.  **合理–**
    这个计划是合理的，因为桑奇塔只有一个方法来证明她的诚实，那就是通过她的私人钥匙。
3.  **零知识–**
    萨钦从来没有知道过三奇塔的私钥。