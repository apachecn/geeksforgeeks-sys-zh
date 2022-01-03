# 用中国剩余定理进行弱 RSA 解密

> 原文:[https://www . geesforgeks . org/weak-RSA-解密-中文-余数-定理/](https://www.geeksforgeeks.org/weak-rsa-decryption-chinese-remainder-theorem/)

先决条件: [RSA 算法](https://www.geeksforgeeks.org/rsa-algorithm-cryptography/)

**为什么 RSA 解密慢？**
RSA 解密比加密慢，因为在做解密的时候，私钥参数“d”必然很大。此外，参数“p 和 q”是两个非常大的素数。

给定整数 c，e，p 和 q，求 m 使得 **c =幂(m，e) mod (p * q)** (弱整数的 RSA 解密)。

> **基础:**
> 
> *   RSA 是一种公钥加密系统，用于消息的安全传输。
> *   RSA 通常包括四个步骤:
>     (1)密钥生成
>     (2)密钥分发
>     (3)加密
>     (4)解密
> *   消息**加密**是用“公钥”完成的。
> *   消息**解密**是用一个“私钥”完成的——参数(p，q，d)与公钥一起生成。
> *   私钥只为用户所知，而公钥可以为任何希望用相应私钥向其发送加密消息的人所知。
> *   由两个参数 n(模)和 e(指数)描述的公钥。模数是两个非常大的素数(p 和 q，如下所示)的乘积。解密此消息将需要用户将 n 分解为两个质因数(主要原因是 RSA 是安全的)，然后找到 e 的模逆，这是困难的任务所在。
> *   文本消息首先被转换为相应的十进制值，这是我们在下面找到的参数“m”。我们现在通过执行 **c = pow(m，e) mod (p * q)** 来加密该消息，其中 c 是加密文本。

在这段代码中，我们利用弱模和指数值，通过找到 p、q 和 d 的值来生成私钥，从而尝试破解加密。在这些示例中，我们将尝试在给定 p 和 q 的情况下找到 d。

**注意:**
在这里，在这个例子中我们使用的是 **p** 和 **q** 的小值，但实际上我们使用的是 **p** 和 **q** 的非常大的值，以确保我们的 RSA 系统的安全。

**示例:**

```
Input : 
c = 1614
e = 65537
p = 53
q = 31

Output :
1372

Explanation :
We calculate c = pow(m, e)mod(p * q). 
Insert m = 1372\. 
On calculating, we get c = 1614.

Input : 
c = 3893595
e = 101
p = 3191
q = 3203

Output :
6574839

Explanation :
As shown above, if we calculate pow(m, e)mod(p * q)
with m = 6574839, we get c = 3893595

```

> 通常，我们可以通过以下步骤找到 m 的值:
> 
> (1)计算 e.
> 的模逆我们可以利用下面的等式，**d = e^(-1)(modλ(n))**，
> 其中λ是 **Carmichael 全能性函数**。
> **读取** : [卡迈克尔功能](https://en.wikipedia.org/wiki/Carmichael_function)
> 
> (2)计算 **m =功率(c，d)mod(p * q)**
> 
> (3)我们可以通过使用如下函数
> 中定义的中国剩余定理
> 来更快地执行该计算。关于中国剩余定理的进一步阅读可以在
> [RSA(密码系统)](https://en.wikipedia.org/wiki/RSA_(cryptosystem))完成

下面是这种方法的 Python 实现:

```
# Function to find the gcd of two 
# integers using Euclidean algorithm
def gcd(p, q):

    if q == 0:
        return p

    return gcd(q, p % q)

# Function to find the
# lcm of two integers 
def lcm(p, q):
    return p * q / gcd(p, q)

# Function implementing extended
# euclidean algorithm
def egcd(e, phi):

    if e == 0:
        return (phi, 0, 1)
    else:
        g, y, x = egcd(phi % e, e)
        return (g, x - (phi // e) * y, y)

# Function to compute the modular inverse
def modinv(e, phi):

    g, x, y = egcd(e, phi)
    return x % phi

# Implementation of the Chinese Remainder Theorem
def chineseremaindertheorem(dq, dp, p, q, c):

    # Message part 1
    m1 = pow(c, dp, p)

    # Message part 2
    m2 = pow(c, dq, q)

    qinv = modinv(q, p)
    h = (qinv * (m1 - m2)) % p
    m = m2 + h * q
    return m

# Driver Code
p = 9817
q = 9907
e = 65537
c = 36076319
d = modinv(e, lcm(p - 1, q - 1))

"""
pow(a, b, c) calculates a raised to power b 
modulus c, at a much faster rate than pow(a, b) % c
Furthermore, we use Chinese Remainder Theorem as it
splits the equation such that we have to calculate two
values whose equations have smaller moduli and exponent  
value, thereby reducing computing time.
"""

dq = pow(d, 1, q - 1)
dp = pow(d, 1, p - 1)
print chineseremaindertheorem(dq, dp, p, q, c)
```

**输出:**

```
41892906

```