# 八进制到十进制转换程序

> 原文:[https://www . geesforgeks . org/program-八进制-十进制-转换/](https://www.geeksforgeeks.org/program-octal-decimal-conversion/)

给定一个八进制数作为输入，我们需要编写一个程序，将给定的八进制数转换成等价的十进制数。

**示例:**

```
Input : 67
Output: 55

Input : 512
Output: 330

Input : 123
Output: 83
```

其思想是从最右边的数字开始提取给定八进制数的数字，并保留一个变量 dec_value。从八进制数中提取数字时，将该数字与适当的基数(8 的幂)相乘，并将其添加到变量 dec_value 中。最后，变量 dec_value 将存储所需的十进制数。

例如:

如果八进制数是 67。

dec_value = 6*(8^1) + 7*(8^0) = 55

下图说明了如何将八进制数(123)转换为等效的十进制值:

![](img/6324d93321c305cf0cdfc76b0b13cdea.png)

以下是上述想法的实现。

## C++

```
// C++ program to convert octal to decimal
#include <iostream>
using namespace std;

// Function to convert octal to decimal
int octalToDecimal(int n)
{
    int num = n;
    int dec_value = 0;

    // Initializing base value to 1, i.e 8^0
    int base = 1;

    int temp = num;
    while (temp) {

        // Extracting last digit
        int last_digit = temp % 10;
        temp = temp / 10;

        // Multiplying last digit with appropriate
        // base value and adding it to dec_value
        dec_value += last_digit * base;

        base = base * 8;
    }

    return dec_value;
}

// Driver program to test above function
int main()
{
    int num = 67;

    cout << octalToDecimal(num) << endl;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert octal to decimal
import java.io.*;

class GFG {

    // Function to convert octal to decimal
    static int octalToDecimal(int n)
    {
        int num = n;
        int dec_value = 0;

        // Initializing base value to 1, i.e 8^0
        int base = 1;

        int temp = num;
        while (temp > 0) {
            // Extracting last digit
            int last_digit = temp % 10;
            temp = temp / 10;

            // Multiplying last digit with appropriate
            // base value and adding it to dec_value
            dec_value += last_digit * base;

            base = base * 8;
        }
        return dec_value;
    }

    // driver program
    public static void main(String[] args)
    {
        int num = 67;
        System.out.println(octalToDecimal(num));
    }
}

// This code is contributed
// by Pramod Kumar
```

## 蟒蛇 3

```
# Python3 program to convert
# octal to decimal

# Function to convert
# octal to decimal

def octalToDecimal(n):

    num = n
    dec_value = 0

    # Initializing base value
    # to 1, i.e 8^0
    base = 1

    temp = num
    while (temp):

        # Extracting last digit
        last_digit = temp % 10
        temp = int(temp / 10)

        # Multiplying last digit
        # with appropriate base
        # value and adding it
        # to dec_value
        dec_value += last_digit * base

        base = base * 8

    return dec_value

# Driver Code
num = 67
print(octalToDecimal(num))

# This code is contributed by mits
```

## C#

```
// C# program to convert octal to
// decimal
using System;

class GFG {

    // Function to convert octal
    // to decimal
    static int octalToDecimal(int n)
    {
        int num = n;
        int dec_value = 0;

        // Initializing base value
        // to 1, i.e 8^0
        int b_ase = 1;

        int temp = num;
        while (temp > 0) {

            // Extracting last digit
            int last_digit = temp % 10;
            temp = temp / 10;

            // Multiplying last digit
            // with appropriate base
            // value and adding it to
            // dec_value
            dec_value += last_digit * b_ase;

            b_ase = b_ase * 8;
        }
        return dec_value;
    }

    // driver program
    public static void Main()
    {
        int num = 67;

        Console.WriteLine(octalToDecimal(num));
    }
}

// This code is contributed by vt_m.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP program to convert octal to decimal

// Function to convert
// octal to decimal
function octalToDecimal($n)
{

    $num = $n;
    $dec_value = 0;

    // Initializing base value
    // to 1, i.e 8^0
    $base = 1;

    $temp = $num;
    while ($temp)
    {

        // Extracting last digit
        $last_digit = $temp % 10;
        $temp = $temp / 10;

        // Multiplying last digit
        // with appropriate base
        // value and adding it
        // to dec_value
        $dec_value += $last_digit * $base;

        $base = $base * 8;
    }

    return $dec_value;
}

    // Driver Code
    $num = 67;
    echo octalToDecimal($num);

// This code is contributed by anuj_67
?>
```

## java 描述语言

```
<script>

// JavaScript program to convert octal to decimal

// Function to convert octal to decimal
function octalToDecimal(n)
{
    let num = n;
    let dec_value = 0;

    // Initializing base value to 1, i.e 8^0
    let base = 1;

    let temp = num;
    while (temp) {

        // Extracting last digit
        let last_digit = temp % 10;
        temp = Math.floor(temp / 10);

        // Multiplying last digit with appropriate
        // base value and adding it to dec_value
        dec_value += last_digit * base;

        base = base * 8;
    }

    return dec_value;
}

// Driver program to test above function

    let num = 67;

    document.write(octalToDecimal(num) + "<br>");

// This code is contributed by Surbhi Tyagi

</script>
```

**Output**

```
55
```

**使用预定义功能**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert octal to decimal
import java.io.*;

class GFG {
    public static int OctToDec(String n)
    {
        return Integer.parseInt(n, 8);
    }
    public static void main(String[] args)
    {

        String n = "67";
        System.out.println(OctToDec(n));
    }
}
```

## 蟒蛇 3

```
# Python program to convert octal to decimal
def OctToDec(n):
    return int(n, 8);

if __name__ == '__main__':

    n = "67";
    print(OctToDec(n));

# This code is contributed by 29AjayKumar
```

## C#

```
using System;

public class GFG{

    public static int OctToDec(String n)
    {
        return Convert.ToInt32(n, 8);
    }

    static public void Main (){

        string n = "67";
        Console.WriteLine(OctToDec(n));
    }
}

// THIS CODE IS CONTRIBUTED BY RAG2127
```

## java 描述语言

```
<script>
// javascript program to convert octal to decimal
   function OctToDec(n)
    {
        return parseInt(n, 8);
    }

   var n = "67";
   document.write(OctToDec(n));
// This code contributed by Princi Singh
</script>
```

**Output**

```
55
```

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。