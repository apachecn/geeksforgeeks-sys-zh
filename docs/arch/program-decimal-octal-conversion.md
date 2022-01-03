# 十进制到八进制转换程序

> 原文:[https://www . geesforgeks . org/program-十进制-八进制-转换/](https://www.geeksforgeeks.org/program-decimal-octal-conversion/)

给定一个十进制数作为输入，我们需要编写一个程序，将给定的十进制数转换成等价的八进制数。即将基值为 10 的数字转换为基值 8。数字系统的基值决定了用于表示数值的位数。例如，二进制数字系统使用两位数字 0 和 1，八进制数字系统使用 0-7 中的 8 位数字，十进制数字系统使用 10 位数字 0-9 来表示任何数值。

**示例:**

```
Input : 16
Output: 20

Input : 10
Output: 12

Input : 33
Output: 41
```

### **算法**:

1.  当数组中的数字被 8 除时，存储余数。
2.  现在把这个数除以 8
3.  重复以上两个步骤，直到数字不等于 0。
4.  现在以相反的顺序打印数组。

例如:

如果给定的十进制数是 16。

**第 1 步**:16 除以 8 的余数为 0。因此，arr[0] = 0。
**第二步**:16 除以 8。新数字是 16/8 = 2。
**第三步**:余数，2 除以 8，就是 2。因此，arr[1] = 2。
**第四步**:2 除以 8。新数字是 2/8 = 0。
**第五步**:因为数字变成= 0。

停止重复步骤，并以相反的顺序打印数组。因此，等效的八进制数是 20。

下图显示了将十进制数 33 转换为等效八进制数的示例。

![decToOctal](img/b04a4c6f6889a3f77f23362ec3be079e.png)

以下是上述想法的实现。

## C++

```
// C++ program to convert a decimal
// number to octal number

#include <iostream>
using namespace std;

// function to convert decimal to octal
void decToOctal(int n)
{

    // array to store octal number
    int octalNum[100];

    // counter for octal number array
    int i = 0;
    while (n != 0) {

        // storing remainder in octal array
        octalNum[i] = n % 8;
        n = n / 8;
        i++;
    }

    // printing octal number array in reverse order
    for (int j = i - 1; j >= 0; j--)
        cout << octalNum[j];
}

// Driver Code
int main()
{
    int n = 33;

    // Function Call
    decToOctal(n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert a decimal
// number to octal number
import java.io.*;

class GFG {
    // Function to convert decimal to octal
    static void decToOctal(int n)
    {
        // array to store octal number
        int[] octalNum = new int[100];

        // counter for octal number array
        int i = 0;
        while (n != 0) {
            // storing remainder in octal array
            octalNum[i] = n % 8;
            n = n / 8;
            i++;
        }

        // Printing octal number array in reverse order
        for (int j = i - 1; j >= 0; j--)
            System.out.print(octalNum[j]);
    }

    // Driver Code
    public static void main(String[] args)
    {
        int n = 33;

        // Function Call
        decToOctal(n);
    }
}

// Contributed by Pramod Kumar
```

## 蟒蛇 3

```
# Python3 program to convert
# a decimal number to
# octal number

# function to convert
# decimal to octal

def decToOctal(n):

    # array to store
    # octal number
    octalNum = [0] * 100

    # counter for octal
    # number array
    i = 0
    while (n != 0):

        # storing remainder
        # in octal array
        octalNum[i] = n % 8
        n = int(n / 8)
        i += 1

    # printing octal number
    # array in reverse order
    for j in range(i - 1, -1, -1):
        print(octalNum[j], end="")

# Driver Code
n = 33

# Function Call
decToOctal(n)

# This code is contributed
# by mits
```

## C#

```
// C# program to convert a decimal
// number to octal number
using System;

class GFG {

    // Function to convert decimal to octal
    static void decToOctal(int n)
    {

        // array to store octal number
        int[] octalNum = new int[100];

        // counter for octal number array
        int i = 0;
        while (n != 0) {

            // storing remainder in octal array
            octalNum[i] = n % 8;
            n = n / 8;
            i++;
        }

        // Printing octal number array in
        // reverse order
        for (int j = i - 1; j >= 0; j--)
            Console.Write(octalNum[j]);
    }

    // Driver Code
    public static void Main()
    {
        int n = 33;

        // Function Call
        decToOctal(n);
    }
}

// This code is contributed by nitin mittal.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP program to convert
// a decimal number to
// octal number

// function to convert
// decimal to octal
function decToOctal($n)
{

    // array to store
    // octal number
    $octalNum;

    // counter for octal
    // number array
    $i = 0;
    while ($n != 0)
    {

        // storing remainder
        // in octal array
        $octalNum[$i] = $n % 8;
        $n = (int)($n / 8);
        $i++;
    }

    // printing octal number
    // array in reverse order
    for ( $j = $i - 1; $j >= 0; $j--)
        echo $octalNum[$j];
}

// Driver Code
$n = 33;

// Function Call
decToOctal($n);

// This code is contributed
// by ajit
?>
```

## java 描述语言

```
<script>

// JavaScript program to convert a decimal
// number to octal number

// function to convert decimal to octal
function decToOctal(n)
{

    // array to store octal number
    let octalNum = new Array(100);

    // counter for octal number array
    let i = 0;
    while (n != 0) {

        // storing remainder in octal array
        octalNum[i] = n % 8;
        n = Math.floor(n / 8);
        i++;
    }

    // printing octal number array in reverse order
    for (let j = i - 1; j >= 0; j--)
        document.write(octalNum[j]);
}

// Driver Code
    let n = 33;

    // Function Call
    decToOctal(n);

// This code is contributed by Surbhi Tyagi

</script>
```

**Output**

```
41
```

#### **时间复杂度:** O(对数 N)

### **另一种方法:(O(1)空间复杂度)**

这个问题也可以在不使用阵列的情况下使用以下算法来解决:

*   将八进制数初始化为 0，将 countVal 初始化为 1，将十进制数初始化为 n
*   当十进制数除以 8 时求余数
*   用八进制+(余数* countval)更新八进制数
*   将 countval 增加 countval*10
*   十进制数除以 8
*   从第二步开始重复，直到十进制数为零

下面是上述想法的实现:

## C++

```
// C++ program to convert decimal
// number to octal number
#include <iostream>
using namespace std;

// function to calculate the octal value of the given
// decimal number
void decimaltoOctal(int deciNum)
{

    // initializations
    int octalNum = 0, countval = 1;
    int dNo = deciNum;

    while (deciNum != 0) {

        // decimals remainder is calculated
        int remainder = deciNum % 8;

        // storing the octalvalue
        octalNum += remainder * countval;

        // storing exponential value
        countval = countval * 10;
        deciNum /= 8;
    }
    cout << octalNum << endl;
}

// Driver Code
int main()
{
    int n = 33;

    // Function Call
    decimaltoOctal(n);
    return 0;
}
```

## C

```
// C program to convert decimal
// number to octal number
#include <stdio.h>

// function to calculate the octal value of the given
// decimal number
void decimaltoOctal(int deciNum)
{

    int octalNum = 0, countval = 1;
    int dNo = deciNum;

    while (deciNum != 0) {
        // decimals remainder is calculated
        int remainder = deciNum % 8;

        // storing the octalvalue
        octalNum += remainder * countval;

        // storing exponential value
        countval = countval * 10;
        deciNum /= 8;
    }
    printf("%d", octalNum);
}

// Driver Code
int main()
{
    int n = 33;

    // Function Call
    decimaltoOctal(n);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// JAVA program to convert decimal
// number to octal number

import java.io.*;

class GFG {
    // function to calculate the octal value of the given
    // decimal number
    static void octaltodecimal(int deciNum)
    {
        int octalNum = 0, countval = 1;
        int dNo = deciNum;
        while (deciNum != 0) {

            // decimals remainder is calculated
            int remainder = deciNum % 8;

            // storing the octalvalue
            octalNum += remainder * countval;

            // storing exponential value
            countval = countval * 10;
            deciNum /= 8;
        }
        System.out.println(octalNum);
    }

    // Driver Code
    public static void main(String[] args)
    {
        int n = 33;

        // Function Call
        octaltodecimal(n);
    }
}
```

## 蟒蛇 3

```
# Python3 program to convert decimal
# number to octal number

# function to calculate the octal value of the given
# decimal number

def decimaltoOctal(deciNum):

    # initializations
    octalNum = 0
    countval = 1
    dNo = deciNum

    while (deciNum != 0):

        # decimals remainder is calculated
        remainder = deciNum % 8

        # storing the octalvalue
        octalNum += remainder * countval

        # storing exponential value
        countval = countval * 10
        deciNum //= 8

    print(octalNum)

# Driver Code
if __name__ == '__main__':

    n = 33

    # Function Call
    decimaltoOctal(n)

# This code is contributed by pratham76
```

## C#

```
// C# program to convert decimal
// number to octal number
using System;
class GFG {

    // function to calculate
    // the octal value of the given
    // decimal number
    static void octaltodecimal(int deciNum)
    {
        int octalNum = 0, countval = 1;

        while (deciNum != 0) {
            // decimals remainder is
            // calculated
            int remainder = deciNum % 8;

            // storing the octalvalue
            octalNum += remainder * countval;

            // storing exponential value
            countval = countval * 10;
            deciNum /= 8;
        }
        Console.Write(octalNum);
    }

    // Driver Code
    public static void Main(string[] args)
    {
        int n = 33;

        // Function Call
        octaltodecimal(n);
    }
}

// This code is contributed by rutvik_56
```

## java 描述语言

```
<script>

// Javascript program to convert decimal
// number to octal number

// function to calculate the octal value of the given
// decimal number
function decimaltoOctal(deciNum)
{

    // initializations
    let octalNum = 0, countval = 1;
    let dNo = deciNum;

    while (deciNum != 0) {

        // decimals remainder is calculated
        let remainder = Math.floor(deciNum % 8);

        // storing the octalvalue
        octalNum += remainder * countval;

        // storing exponential value
        countval = countval * 10;
        deciNum = Math.floor(deciNum/8);
    }
    document.write(octalNum + "<br>");
}

// Driver Code
    let n = 33;

    // Function Call
    decimaltoOctal(n);

//This code is contributed by Mayank Tyagi

</script>
```

**Output**

```
41
```

**时间复杂度:** O(对数 N)

**辅助空间:** O(1)

**使用预定义功能**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// JAVA program to convert decimal
// number to octal number
import java.io.*;

class GFG {
    public static void decToOct(int n)
    {
        System.out.println(Integer.toOctalString(n));
    }
    public static void main(String[] args)
    {

        int n = 33;
        decToOct(n);
    }
}
```

## 蟒蛇 3

```
# Python program to convert decimal
# number to octal number

def decToOct(n):
    print(oct(n));

if __name__ == '__main__':

    n = 33;
    decToOct(n);

# This code is contributed by Amit Katiyar
```

## C#

```
// C# program to convert decimal
// number to octal number
using System;

public class GFG
{
    public static void decToOct(int n)
    {
        Console.WriteLine(Convert.ToString(n, 8));
    }
    public static void Main(String[] args)
    {

        int n = 33;
        decToOct(n);
    }
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```
<script>

// Javascript program to convert decimal
// number to octal number
function decToOct(n)
{
    document.write(n.toString(8));
}

var n = 33;
decToOct(n);

// This code contributed by Princi Singh

</script>
```

## C++

```
#include <bits/stdc++.h>
using namespace std;

string intToOctal(int n)
{
    stringstream st;
    st << oct << n;
    return st.str();
}

int main()
{
    int n = 43;
    cout << intToOctal(n);
    return 0;
}
```

**Output**

```
41
```

本文由绍拉布·夏尔马供稿。如果你喜欢极客博客并想投稿，你也可以用 write.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。