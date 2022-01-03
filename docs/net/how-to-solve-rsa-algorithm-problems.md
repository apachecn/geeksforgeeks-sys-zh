# 如何解决 RSA 算法问题？

> 原文:[https://www . geesforgeks . org/how-to-solution-RSA-algorithm-problems/](https://www.geeksforgeeks.org/how-to-solve-rsa-algorithm-problems/)

[RSA 算法](https://www.geeksforgeeks.org/rsa-algorithm-cryptography/)是一种非对称密码算法，这意味着在通信时应该有两个密钥参与，即公钥和私钥。有一些简单的步骤可以解决 RSA 算法中的问题。

**示例-1:**

*   **第一步:选择两个质数** ![p](img/e1eed83fb4737e3780aa1efabe94d327.png "Rendered by QuickLaTeX.com")和![q](img/aa43b7964339c8af509f742427dccd41.png "Rendered by QuickLaTeX.com")
    让我们取![p = 3](img/8ae0ee92dbbc0df2a9762344cdbd6676.png "Rendered by QuickLaTeX.com")和![q = 11](img/81bd3725b42151c0bdd231d351bbf836.png "Rendered by QuickLaTeX.com")
*   **第二步:计算**![n](img/42ce0a847b20a2f8a781c8a50bdab975.png "Rendered by QuickLaTeX.com")![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com")
    的值，给出如下:

```
 and 
```

这里的例子中，
![n = 3 \times 11 = 33](img/589a5e3915fb936705f822a4ab7cd8e1.png "Rendered by QuickLaTeX.com")
![\phi = (3-1) \times (11-1) = 2 \times 10 = 20](img/59032f6e7eb4c4f4dea3f29a83e7e48c.png "Rendered by QuickLaTeX.com")

*   **Step-3: Find the value of** ![e](img/836bdfb5b79b6fa63bc42d7c99d1bc9d.png "Rendered by QuickLaTeX.com") **(public key)**
    Choose ![e](img/836bdfb5b79b6fa63bc42d7c99d1bc9d.png "Rendered by QuickLaTeX.com"), such that ![e](img/836bdfb5b79b6fa63bc42d7c99d1bc9d.png "Rendered by QuickLaTeX.com") should be co-prime. Co-prime means it should not multiply by factors of ![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com") and also not divide by ![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com")

    ![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com")的因子是，![20 = 5 \times 4 = 5 \times 2 \times 2](img/5b9130ec70ae6c529ccab864ad06c2f5.png "Rendered by QuickLaTeX.com")所以![e](img/836bdfb5b79b6fa63bc42d7c99d1bc9d.png "Rendered by QuickLaTeX.com")不要乘以![5](img/f089f65846f230191554fc4f034603fb.png "Rendered by QuickLaTeX.com")和![2](img/b8fbaaf9242360e81ed136b06f3e35b4.png "Rendered by QuickLaTeX.com")，不要除以 20。

    所以，质数是 3，7，11，17，19…，当取 3 和 11 时，选择![e](img/836bdfb5b79b6fa63bc42d7c99d1bc9d.png "Rendered by QuickLaTeX.com")作为 7

    因此，![e = 7](img/bbeb89bc2ffe3d7e9773ba533a7e9b03.png "Rendered by QuickLaTeX.com")

    *   **Step-4: Compute the value of** ![d](img/63d187c3ece213ac5b6bceea415b2bb8.png "Rendered by QuickLaTeX.com") **(private key)**
    The condition is given as,
    ![gcd(\phi, e) = \phi x +ey = 1](img/47f565c7c198718100a7cecd2ec600cc.png "Rendered by QuickLaTeX.com") where y is the value of ![d](img/63d187c3ece213ac5b6bceea415b2bb8.png "Rendered by QuickLaTeX.com").

    要计算![d](img/63d187c3ece213ac5b6bceea415b2bb8.png "Rendered by QuickLaTeX.com")的值，

    1.  形成一个有四列的表格，即 a、b、d 和 k。
    2.  初始化 a = 1，b = 0，d = ![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com")，k =–第一行。
    3.  初始化第二行的 a = 0，b = 1，d = ![e](img/836bdfb5b79b6fa63bc42d7c99d1bc9d.png "Rendered by QuickLaTeX.com")，![k = \frac{\phi}{e}](img/2233735b81c421848bf866162f7c3be0.png "Rendered by QuickLaTeX.com")。
    4.  从下一行，应用以下公式计算下一个 a、b、d 和 k 的值，如下所示
        *   ![a_{i} = a_{i-2} - (a_{i-1} \times k_{i-1})](img/0d6ca03e0efb49ea637589feab3cd6ec.png "Rendered by QuickLaTeX.com")
        *   ![b_{i} = b_{i-2} - (b_{i-1} \times k_{i-1})](img/08ea4f0468c29778e3847c65dbe1e94d.png "Rendered by QuickLaTeX.com")
        *   ![d_{i} = d_{i-2} - (d_{i-1} \times k_{i-1})](img/670b4c8bd73280461e2e65ab6e6bf951.png "Rendered by QuickLaTeX.com")
        *   ![k_{i} = \frac{d_{i-1}}{d_{i}}](img/1d303bba8e0c1860c7d099383dcd7d71.png "Rendered by QuickLaTeX.com")

    一旦![d = 1](img/7d9492183b26395765a7cbb80f361c52.png "Rendered by QuickLaTeX.com")，停止该过程并检查以下情况

    ```
    if 

    if 

    ```

    对于给定的示例，该表将是，

    | a | b | d | k |
    | --- | --- | --- | --- |
    | one | Zero | Twenty | – |
    | Zero | one | seven | Two |
    | one | -2 | six | one |
    | -1 | three | one | – |

    如上表![d = 1](img/7d9492183b26395765a7cbb80f361c52.png "Rendered by QuickLaTeX.com")所示，停止该过程并检查为![b](img/2756c6910b6252c720a4eb054b296013.png "Rendered by QuickLaTeX.com")
    ![\therefore b = 3](img/0f74e77e2f0b380bf7d5dd43422c362a.png "Rendered by QuickLaTeX.com")给出的条件

    要验证![b](img/2756c6910b6252c720a4eb054b296013.png "Rendered by QuickLaTeX.com")是否正确，应满足上述条件，即
    ![gcd(\phi, e) = \phi x + ey = (20 \times -1) + (7 \times 3) = 1](img/beeb8e3b65bf20fffb239618225e880c.png "Rendered by QuickLaTeX.com")。因此![d](img/63d187c3ece213ac5b6bceea415b2bb8.png "Rendered by QuickLaTeX.com")是正确的。

    *   **Step-5: Do the encryption and decryption**
    Encryption is given as,
    ![c = t^{e}\mod n](img/20e020dba2261b88526fb27268fb6430.png "Rendered by QuickLaTeX.com")
    Decryption is given as,
    ![t = c^{d}\mod n](img/a718b73bb3f9566e31764028dc40634b.png "Rendered by QuickLaTeX.com")

    举个例子，假设![t = 2](img/0882dc8515e4d6c69a4180415ac987b1.png "Rendered by QuickLaTeX.com")，那么
    加密就是![c = 2^{7}\mod 33 = 29](img/4cfc2bdb54afd9412fe5a799dccbd2a5.png "Rendered by QuickLaTeX.com")

    解密是![t = 29^{3}\mod 33 = 2](img/14171a27f6f11f5fc4048af3e446b962.png "Rendered by QuickLaTeX.com")

    因此在决赛中，![p = 3](img/8ae0ee92dbbc0df2a9762344cdbd6676.png "Rendered by QuickLaTeX.com")、![q = 11](img/81bd3725b42151c0bdd231d351bbf836.png "Rendered by QuickLaTeX.com")、![\phi = 20](img/51878f83710ebacc5b004515ad0baa1f.png "Rendered by QuickLaTeX.com")、![n = 33](img/820211885feb401b1b8da9f0ff88f53d.png "Rendered by QuickLaTeX.com")、![e = 7](img/bbeb89bc2ffe3d7e9773ba533a7e9b03.png "Rendered by QuickLaTeX.com")和![d = 3](img/820d1561ccf80f2b9894172848d9c981.png "Rendered by QuickLaTeX.com")

    **示例-2:[GATE CS-2017(Set 1)](https://www.geeksforgeeks.org/gate-gate-cs-2017-set-1-question-44/)**
    在 RSA 密码系统中，特定的 A 使用两个素数 p = 13 和 q =17 来生成她的公钥和私钥。如果 A 的公钥是 35。那么 A 的私钥是？

    1.  ![p = 13](img/bac77ae51478d5de2a1783633d087ae3.png "Rendered by QuickLaTeX.com")和![q = 17](img/4d714b23b640701f51c2a80fade9f2ad.png "Rendered by QuickLaTeX.com")
    2.  计算![n = 13 \times 17 = 221](img/74b05872f142a8ed1429d02c1f0c3c44.png "Rendered by QuickLaTeX.com")和![\phi = (13-1) \times (17-1) = 12 \times 16 = 192](img/87438769609b2a846c9755923c9a8c98.png "Rendered by QuickLaTeX.com")
    3.  ![e = 35](img/501efa6e08d4c10bb4993ea47db3c92a.png "Rendered by QuickLaTeX.com")(公钥)
    4.  Compute ![d](img/63d187c3ece213ac5b6bceea415b2bb8.png "Rendered by QuickLaTeX.com") (private key)

        | a | b | d | k |
        | --- | --- | --- | --- |
        | one | Zero | One hundred and ninety-two | – |
        | Zero | one | Thirty-five | five |
        | one | -5 | Seventeen | Two |
        | -2 | Eleven | one | – |

        ![\therefore d = 11](img/264775693d731b35907e0d0df9a18242.png "Rendered by QuickLaTeX.com")(私钥)