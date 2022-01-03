# ElGamal 加密算法

> 原文:[https://www.geeksforgeeks.org/elgamal-encryption-algorithm/](https://www.geeksforgeeks.org/elgamal-encryption-algorithm/)

**ElGamal 加密**是一种公钥密码系统。它使用非对称密钥加密在双方之间进行通信并加密消息。
这个密码系统是基于在循环群中寻找**离散对数**的难度，也就是说即使我们知道 g <sup>a</sup> 和 g <sup>k</sup> ，也极难计算 g <sup>ak</sup> 。
**ElGamal 密码系统的想法**
假设爱丽丝想和鲍勃通信。

1.  Bob 生成公钥和私钥:
    *   Bob 选择一个非常大的数字 **q** 和一个循环组**F**T4【q】T5】。
    *   从循环组 **F** <sub>q</sub> 中，他选择任意元素 **g** 和
        a 元素 **a** ，使得 gcd(a，q) = 1。
    *   然后他计算 h = g <sup>a</sup> 。
    *   Bob 将 **F** 、 **h = g <sup>a</sup>** 、 **q** 和 **g** 发布为自己的公钥，并将 **a** 保留为私钥。
2.  爱丽丝使用鲍勃的公钥加密数据:
    *   Alice 从循环组 **F**
        中选择一个元素 **k** ，使得 gcd(k，q) = 1。
    *   然后她计算 p = g <sup>k</sup> 和 s = h <sup>k</sup> = g <sup>ak。</sup>
    *   她是 m 的倍数。
    *   然后她发送(p，M*s) = (g <sup>k</sup> ，M*s)。
3.  鲍勃解密了这条消息:
    *   鲍勃计算 s<sup>′</sup>= p<sup>a</sup>= g<sup>AK</sup>。
    *   他将 M*s 除以 s<sup>′</sup>，得到 M 为 s = s<sup>′</sup>。

**下面是 ElGamal 密码系统在 Python 中的实现**

## 蟒蛇 3

```
# Python program to illustrate ElGamal encryption

import random
from math import pow

a = random.randint(2, 10)

def gcd(a, b):
    if a < b:
        return gcd(b, a)
    elif a % b == 0:
        return b;
    else:
        return gcd(b, a % b)

# Generating large random numbers
def gen_key(q):

    key = random.randint(pow(10, 20), q)
    while gcd(q, key) != 1:
        key = random.randint(pow(10, 20), q)

    return key

# Modular exponentiation
def power(a, b, c):
    x = 1
    y = a

    while b > 0:
        if b % 2 != 0:
            x = (x * y) % c;
        y = (y * y) % c
        b = int(b / 2)

    return x % c

# Asymmetric encryption
def encrypt(msg, q, h, g):

    en_msg = []

    k = gen_key(q)# Private key for sender
    s = power(h, k, q)
    p = power(g, k, q)

    for i in range(0, len(msg)):
        en_msg.append(msg[i])

    print("g^k used : ", p)
    print("g^ak used : ", s)
    for i in range(0, len(en_msg)):
        en_msg[i] = s * ord(en_msg[i])

    return en_msg, p

def decrypt(en_msg, p, key, q):

    dr_msg = []
    h = power(p, key, q)
    for i in range(0, len(en_msg)):
        dr_msg.append(chr(int(en_msg[i]/h)))

    return dr_msg

# Driver code
def main():

    msg = 'encryption'
    print("Original Message :", msg)

    q = random.randint(pow(10, 20), pow(10, 50))
    g = random.randint(2, q)

    key = gen_key(q)# Private key for receiver
    h = power(g, key, q)
    print("g used : ", g)
    print("g^a used : ", h)

    en_msg, p = encrypt(msg, q, h, g)
    dr_msg = decrypt(en_msg, p, key, q)
    dmsg = ''.join(dr_msg)
    print("Decrypted Message :", dmsg);

if __name__ == '__main__':
    main()
```

样本输出:

```
Original Message : encryption
g used :  5860696954522417707188952371547944035333315907890
g^a used :  4711309755639364289552454834506215144653958055252
g^k used :  12475188089503227615789015740709091911412567126782
g^ak used :  39448787632167136161153337226654906357756740068295
Decrypted Message : encryption
```

在这个密码系统中，原始消息 **M** 通过将**g<sup>AK</sup>T5】相乘来屏蔽。取下面具，以 **g <sup>k</sup>** 的形式给出线索。除非有人知道 **a** ，否则他将无法取回 **M** 。这是因为在一个循环组中寻找离散对数比较困难，而且要简化知道 g <sup>a</sup> 和 g <sup>k</sup> 还不足以计算 g <sup>ak</sup> 。**