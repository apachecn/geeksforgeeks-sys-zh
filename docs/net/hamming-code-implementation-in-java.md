# Java 中的汉明码实现

> 原文:[https://www . geesforgeks . org/hamming-code-implementation-in-Java/](https://www.geeksforgeeks.org/hamming-code-implementation-in-java/)

**先决条件:** [海明码](https://www.geeksforgeeks.org/computer-network-hamming-code/)

[汉明码](https://www.geeksforgeeks.org/computer-network-hamming-code/)是一组**纠错码**，可用于检测和纠正数据从发送方移动或存储到接收方时可能出现的错误。这是由 T4 海明公司开发的一种纠错技术。

**示例:**

```
Input: 
message bit = 0101
r1 r2 m1 r4 m2 m3 m4
      0     1  0  1
Output:
Generated codeword :
r1 r2 m1 r4 m2 m3 m4
0  1  0  0  1  0  1

Explanation:
Initially r1, r2, r4 is set to '0'.
r1 = xor of all bits position 
    which has '1' in its 0th-bit position
r2 = xor of all bits
    which has '1' in its 1st-bit position
r3 = xor of all bits
    which has '1' in its 2nd-bit position

```

下面是汉明码的实现:

```
// Java code to implement Hamming Code
class HammingCode {

    // print elements of array
    static void print(int ar[])
    {
        for (int i = 1; i < ar.length; i++) {
            System.out.print(ar[i]);
        }
        System.out.println();
    }

    // calculating value of redundant bits
    static int[] calculation(int[] ar, int r)
    {
        for (int i = 0; i < r; i++) {
            int x = (int)Math.pow(2, i);
            for (int j = 1; j < ar.length; j++) {
                if (((j >> i) & 1) == 1) {
                    if (x != j)
                        ar[x] = ar[x] ^ ar[j];
                }
            }
            System.out.println("r" + x + " = "
                               + ar[x]);
        }

        return ar;
    }

    static int[] generateCode(String str, int M, int r)
    {
        int[] ar = new int[r + M + 1];
        int j = 0;
        for (int i = 1; i < ar.length; i++) {
            if ((Math.ceil(Math.log(i) / Math.log(2))
                 - Math.floor(Math.log(i) / Math.log(2)))
                == 0) {

                // if i == 2^n for n in (0, 1, 2, .....)
                // then ar[i]=0
                // codeword[i] = 0 ----
                // redundant bits are initialized
                // with value 0
                ar[i] = 0;
            }
            else {

                // codeword[i] = dataword[j]
                ar[i] = (int)(str.charAt(j) - '0');
                j++;
            }
        }
        return ar;
    }

    // Driver code
    public static void main(String[] args)
    {

        // input message
        String str = "0101";
        int M = str.length();
        int r = 1;

        while (Math.pow(2, r) < (M + r + 1)) {
            // r is number of redundant bits
            r++;
        }
        int[] ar = generateCode(str, M, r);

        System.out.println("Generated hamming code ");
        ar = calculation(ar, r);
        print(ar);
    }
}
```

**Output:**

```
Generated hamming code 
r1 = 0
r2 = 1
r4 = 0
0100101

```