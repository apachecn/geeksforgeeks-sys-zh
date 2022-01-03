# 十六进制到十进制的程序

> 原文:[https://www . geesforgeks . org/program-for-十六进制转十进制/](https://www.geeksforgeeks.org/program-for-hexadecimal-to-decimal/)

给定一个十六进制数作为输入，我们需要编写一个程序，将给定的十六进制数转换成等价的十进制数。

**示例:**

```
Input : 67
Output: 103

Input : 512
Output: 1298

Input : 123
Output: 291
```

我们知道十六进制数用 16 个符号{0，1，2，4，5，6，7，8，9，A，B，C，D，E，F}来表示所有的数字。这里，(A，B，C，D，E，F)代表(10，11，12，13，14，15)。

其思想是从最右边的数字开始提取给定十六进制数的数字，并保留一个变量 dec_value。从十六进制数中提取数字时，将该数字与适当的基数(16 的幂)相乘，并将其与变量 dec_value 相加。最后，变量 dec_value 将存储所需的十进制数。

例如:如果十六进制数是 1A。
dec _ value = 1*(16^1)+10*(16^0)= 26

下图说明了如何将十六进制数(1AB)转换为等效的十进制值:

![](img/f23a9f7cb33bbe6e7d1e304c54f27e40.png)

以下是上述想法的实现。

## C++

```
// C++ program to convert hexadecimal to decimal
#include <bits/stdc++.h>
using namespace std;

// Function to convert hexadecimal to decimal

int hexadecimalToDecimal(string hexVal)
{
    int len = hexVal.size();

    // Initializing base value to 1, i.e 16^0
    int base = 1;

    int dec_val = 0;

    // Extracting characters as digits from last
    // character
    for (int i = len - 1; i >= 0; i--) {
        // if character lies in '0'-'9', converting
        // it to integral 0-9 by subtracting 48 from
        // ASCII value
        if (hexVal[i] >= '0' && hexVal[i] <= '9') {
            dec_val += (int(hexVal[i]) - 48) * base;

            // incrementing base by power
            base = base * 16;
        }

        // if character lies in 'A'-'F' , converting
        // it to integral 10 - 15 by subtracting 55
        // from ASCII value
        else if (hexVal[i] >= 'A' && hexVal[i] <= 'F') {
            dec_val += (int(hexVal[i]) - 55) * base;

            // incrementing base by power
            base = base * 16;
        }
    }
    return dec_val;
}

// driver program
int main()
{
    string hexNum = "1A";
    cout << (hexadecimalToDecimal(hexNum));

    // This code is contributed by rakeshsahni

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert hexadecimal to decimal
import java.io.*;

class GFG {
    // Function to convert hexadecimal to decimal
    static int hexadecimalToDecimal(String hexVal)
    {
        int len = hexVal.length();

        // Initializing base value to 1, i.e 16^0
        int base = 1;

        int dec_val = 0;

        // Extracting characters as digits from last
        // character
        for (int i = len - 1; i >= 0; i--) {
            // if character lies in '0'-'9', converting
            // it to integral 0-9 by subtracting 48 from
            // ASCII value
            if (hexVal.charAt(i) >= '0'
                && hexVal.charAt(i) <= '9') {
                dec_val += (hexVal.charAt(i) - 48) * base;

                // incrementing base by power
                base = base * 16;
            }

            // if character lies in 'A'-'F' , converting
            // it to integral 10 - 15 by subtracting 55
            // from ASCII value
            else if (hexVal.charAt(i) >= 'A'
                     && hexVal.charAt(i) <= 'F') {
                dec_val += (hexVal.charAt(i) - 55) * base;

                // incrementing base by power
                base = base * 16;
            }
        }
        return dec_val;
    }

    // driver program
    public static void main(String[] args)
    {
        String hexNum = "1A";
        System.out.println(hexadecimalToDecimal(hexNum));
    }
}
```

## 蟒蛇 3

```
# Python3 program to convert
# hexadecimal to decimal

# Function to convert hexadecimal
# to decimal

def hexadecimalToDecimal(hexval):

    # Finding length
    length = len(hexval)

    # Initialize base value to 1,
    # i.e. 16*0
    base = 1
    dec_val = 0

    # Extracting characters as digits
    # from last character
    for i in range(length - 1, -1, -1):

        # If character lies in '0'-'9',
        # converting it to integral 0-9
        # by subtracting 48 from ASCII value
        if hexval[i] >= '0' and hexval[i] <= '9':
            dec_val += (ord(hexval[i]) - 48) * base

            # Incrementing base by power
            base = base * 16

        # If character lies in 'A'-'F',converting
        # it to integral 10-15 by subtracting 55
        # from ASCII value
        elif hexval[i] >= 'A' and hexval[i] <= 'F':
            dec_val += (ord(hexval[i]) - 55) * base

            # Incrementing base by power
            base = base * 16

    return dec_val

# Driver code
if __name__ == '__main__':

    hexnum = '1A'

    print(hexadecimalToDecimal(hexnum))

# This code is contributed by virusbuddah_
```

## C#

```
// C# program to convert
// hexadecimal to decimal
using System;

class GFG {
    // Function to convert
    // hexadecimal to decimal
    static int hexadecimalToDecimal(String hexVal)
    {
        int len = hexVal.Length;

        // Initializing base1 value
        // to 1, i.e 16^0
        int base1 = 1;

        int dec_val = 0;

        // Extracting characters as
        // digits from last character
        for (int i = len - 1; i >= 0; i--) {
            // if character lies in '0'-'9',
            // converting it to integral 0-9
            // by subtracting 48 from ASCII value
            if (hexVal[i] >= '0' && hexVal[i] <= '9') {
                dec_val += (hexVal[i] - 48) * base1;

                // incrementing base1 by power
                base1 = base1 * 16;
            }

            // if character lies in 'A'-'F' ,
            // converting it to integral
            // 10 - 15 by subtracting 55
            // from ASCII value
            else if (hexVal[i] >= 'A' && hexVal[i] <= 'F') {
                dec_val += (hexVal[i] - 55) * base1;

                // incrementing base1 by power
                base1 = base1 * 16;
            }
        }
        return dec_val;
    }

    // Driver Code
    static void Main()
    {
        String hexNum = "1A";
        Console.WriteLine(hexadecimalToDecimal(hexNum));
    }
}

// This code is contributed by mits
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP program to convert
// hexadecimal to decimal

// Function to convert
// hexadecimal to decimal
function hexadecimalToDecimal($hexVal)
{
    $len = strlen($hexVal);

    // Initializing base value
    // to 1, i.e 16^0
    $base = 1;

    $dec_val = 0;

    // Extracting characters as
    // digits from last character
    for ($i = $len - 1; $i >= 0; $i--)
    {
        // if character lies in '0'-'9',
        // converting it to integral 0-9
        // by subtracting 48 from ASCII value.
        if ($hexVal[$i] >= '0' &&
            $hexVal[$i] <= '9')
        {
            $dec_val += (ord($hexVal[$i]) - 48) *
                                         $base;

            // incrementing base by power
            $base = $base * 16;
        }

        // if character lies in 'A'-'F' , 
        // converting it to integral
        // 10 - 15 by subtracting 55
        // from ASCII value
        else if ($hexVal[$i] >= 'A' &&
                 $hexVal[$i] <= 'F')
        {
            $dec_val += (ord($hexVal[$i]) - 55) *
                                         $base;

            // incrementing base by power
            $base = $base * 16;
        }
    }

    return $dec_val;
}

// Driver Code
$hexNum = "1A";
echo hexadecimalToDecimal($hexNum);

// This code is contributed by mits
?>
```

## java 描述语言

```
<script>
// javascript program to convert hexadecimal to decimal
   // Function to convert hexadecimal to decimal

function hexadecimalToDecimal(hexVal)
{
    var len = hexVal.length;

    // Initializing base value to 1, i.e 16^0
    var base = 1;

    var dec_val = 0;

    // Extracting characters as digits from last
    // character
    for (var i = len - 1; i >= 0; i--) {
        // if character lies in '0'-'9', converting
        // it to integral 0-9 by subtracting 48 from
        // ASCII value
        if (hexVal.charAt(i) >= '0'
            && hexVal.charAt(i) <= '9') {
            dec_val += (hexVal.charAt(i).charCodeAt(0) - 48) * base;

            // incrementing base by power
            base = base * 16;
        }

        // if character lies in 'A'-'F' , converting
        // it to integral 10 - 15 by subtracting 55
        // from ASCII value
        else if (hexVal.charAt(i) >= 'A'
                 && hexVal.charAt(i) <= 'F') {
            dec_val += (hexVal.charAt(i).charCodeAt(0) - 55) * base;

            // incrementing base by power
            base = base * 16;
        }
    }
    return dec_val;
}

// driver program
var hexNum = "1A";
document.write(hexadecimalToDecimal(hexNum));

// This code is contributed by 29AjayKumar
</script>
```

**Output**

```
26
```

**使用预定义功能**

## C++

```
// C++ program to convert octal to decimal
#include <bits/stdc++.h>
using namespace std;
int HexToDec(string n) { return stoi(n, 0, 16); }

int main()
{
    string n = "1A";
    cout << HexToDec(n);

    return 0;
}

    // This code is contributed by rakeshsahni
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert hexadecimal to decimal

import java.io.*;

class GFG {
    public static int HexToDec(String n)
    {
        return Integer.parseInt(n, 16);
    }
    public static void main(String[] args)
    {
        String n = "1A";
        System.out.println(HexToDec(n));
    }
}
```

## 蟒蛇 3

```
# Python program to convert hexadecimal to decimal
def HexToDec(n):
    return int(n, 16);

if __name__ == '__main__':
    n = "1A";
    print(HexToDec(n));

# This code is contributed by 29AjayKumar
```

## C#

```
// C# program to convert hexadecimal to decimal

using System;

public class GFG {
    public static int HexToDec(String n)
    {
        return Convert.ToInt32(n, 16);
    }
    public static void Main(String[] args)
    {
        String n = "1A";
        Console.WriteLine(HexToDec(n));
    }
}

// This code is contributed by Amit Katiyar
```

## java 描述语言

```
<script>
// javascript program to convert octal to decimal
function HexToDec(n)
    {
        return parseInt(n, 16);
    }

var n = "1A";
document.write(HexToDec(n));
// This code is contributed by 29AjayKumar
</script>
```

**Output**

```
26
```

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。