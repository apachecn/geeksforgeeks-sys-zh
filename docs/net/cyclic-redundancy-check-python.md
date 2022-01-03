# Python 中的循环冗余校验

> 原文:[https://www . geesforgeks . org/循环冗余校验-python/](https://www.geeksforgeeks.org/cyclic-redundancy-check-python/)

**先决条件:** [了解循环冗余](https://www.geeksforgeeks.org/modulo-2-binary-division/)[套接字编程](https://www.geeksforgeeks.org/socket-programming-python/)

**什么是 CRC？**
循环冗余校验是一种检测通信信道中意外变化/错误的方法。
循环冗余校验使用发送方和接收方均可用的生成多项式。一个示例生成多项式是 x^3 + 1 的形式。这个生成多项式表示密钥 1001。另一个例子是代表键 110 的 x^2 + x。

**例:**
让数据发送的是“EVN”
我们把一个字符串转换成二进制字符串数据。

## 计算机编程语言

```
input_string = "EVN"

# CONVERT string data to binary string data
data = (''.join(format(ord(x), 'b') for x in input_string))
print (data)
```

**Output**

```
100010110101101001110
```