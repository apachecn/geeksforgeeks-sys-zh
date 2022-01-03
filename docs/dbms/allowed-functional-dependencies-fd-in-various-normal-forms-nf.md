# 各种正常形式的允许功能依赖关系

> 原文:[https://www . geesforgeks . org/allowed-functional-dependencies-FD-in-variable-normal-forms-nf/](https://www.geeksforgeeks.org/allowed-functional-dependencies-fd-in-various-normal-forms-nf/)

先决条件–[功能依赖和属性闭包](https://www.geeksforgeeks.org/functional-dependency-and-attribute-closure/)

我们都知道以下几点:

*   Nf does not allow partial dependence.
*   Nf does not allow passing dependencies.
*   BCNF does not allow anything other than super bonds to be a determinant.

让我们检查所有可能的函数依赖关系，找出什么是允许的，什么是不允许的。请注意:prime 属性是任何候选关键字的一部分。非主要属性是不属于任何候选关键字的属性。因此，建议您从给定的函数依赖项中找出所有可能的候选键，并标记质数和非质数属性。

**1。** [**【第二范式(2NF)**](https://www.geeksforgeeks.org/second-normal-form-2nf/) **:**

**不允许的 FDs–**

```
prime -> non prime 
```

如果说你的函数依赖是 A->X 的形式，其中‘A’是一个质数属性而不是一个键，‘X’是非质数属性，那么这样的 FD 在 2NF 中是不允许的。

**允许的 Fds–**

```
Prime -> Prime
Non prime -> Prime/Non prime
Key -> Prime/Non prime
Prime + Non prime combination -> Prime/Non Prime 
```

*   If' a' is a prime attribute (though not a key), it can determine another prime attribute.
*   If' a' is a non-prime attribute, it can determine a prime/non-prime attribute.
*   If' a' is a key, it can determine a prime/non-prime attribute.

**2。** [**第三范式(3NF)**](https://www.geeksforgeeks.org/third-normal-form-3nf/) **:**

**不允许的 FDs–**

```
Prime -> Non prime  (2NF requirement)
Non prime -> Non prime  (3NF special) 
```

**允许的 FD–**

```
Prime -> Prime
Non prime -> Prime 
Key -> Prime/Non prime 
Prime + Non Prime -> Prime/Non prime 
```

**3。** [**博伊斯-科德范式(BCNF)**](https://www.geeksforgeeks.org/boyce-codd-normal-form-bcnf/) **:**

**不允许的 FDs–**

```
Prime -> Non prime  
Non prime -> Non prime  
Prime -> Prime 
Non prime -> Prime
```

**允许–**T0】