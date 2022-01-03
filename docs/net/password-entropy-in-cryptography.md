# 密码学中的密码熵

> 原文:[https://www . geesforgeks . org/password-熵编码/](https://www.geeksforgeeks.org/password-entropy-in-cryptography/)

[密码熵](https://www.geeksforgeeks.org/passwords-entropy-cracking/)是对密码强度或给定密码强度的度量。这是对密码抵御猜测或暴力攻击的有效性的一种度量。它决定了输入的密码是否通用，是否容易破解。它是通过知道字符集(低位字母、高位字母、数字、符号等)来计算的。)和创建的密码长度。它用每个字符的熵位来表示。

**可能密码总数的计算:**

在本文中，您将看到如何借助示例计算给定字符集可以创建的可能密码总数。

**示例-1 :**

考虑以下信息系统的密码策略，其中要求用户从包含小写字母 a-z、大写字母 A-Z 和数字 0-9 的字符集创建至少 5 个字符且最多 7 个字符的密码。计算可以从中创建的可能密码的总数。

**解决方案–**

```
Total characters = 26(a-z) + 26(A-Z) + 10(0-9) = 62
Passwords must be between 5 characters to 7 characters
=> P = possible passwords.
```

**示例-2 :**

考虑以下信息系统的密码策略，其中要求用户从包含小写字母 a-z、大写字母 A-Z 和数字 0-9 的字符集创建至少 5 个字符且最多 7 个字符的密码。使用至少一个数字计算可能密码的总数**，该数字可以从其中创建。**

**解决方案–**

```
Total characters = 26(a-z) + 26(A-Z) + 10(0-9) = 62
Passwords which can be formed without using any digit = 62 - 10 (0-9) = 52
Passwords must be between 5 characters to 7 characters with atleast one digit
=> P =
 possible passwords.
```

**示例-3 :**

现在假设攻击者使用一台测试能力为每秒破解 250 万个密码的机器，并且如果它能够测试密码总数的 75%，则平均会成功。然后计算示例 2 中攻击者破解密码所需的时间。

**解决方案–**

```
Time required = Total number of possible passwords * rate * accuracy
=  days
```

**密码熵的计算:**

在这里，您将看到如何计算密码熵。密码熵的计算公式如下。

```
Password Entropy = (number of characters in character set) * length of the password
```

**示例-4 :**

计算从例 1 中使用的字符集中选择的 **geeksfg123** 的密码熵。

**解决方案–**

```
Number of characters in character set = 62
Length of password = 10 (geeksfg123)
Password Entropy =  bits of entropy per character
```