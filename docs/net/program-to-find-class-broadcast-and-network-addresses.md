# 查找班级、广播和网络地址的程序

> 原文:[https://www . geesforgeks . org/program-to-find-class-broadcast-and-network-address/](https://www.geeksforgeeks.org/program-to-find-class-broadcast-and-network-addresses/)

先决条件–[介绍和有类寻址](https://www.geeksforgeeks.org/ip-addressing-introduction-and-classful-addressing/)、[无类寻址](https://www.geeksforgeeks.org/ip-addressing-classless-addressing/)、
以字符串形式给出有效的 IPv4 地址。任务是确定给定 IPv4 地址的类别，并从中分离出网络和主机标识部分。
**IPv4 地址:**
互联网上的每一台主机和路由器都有一个 IP 地址，它对自己的网络号和主机号进行编码，两者的组合是唯一的。IP 地址实际上不是指主机，而是指网络接口，因此如果主机位于两个网络上，它必须有两个 IP 地址。
**默认掩码:**
地址掩码确定 IP 地址的哪个部分代表网络号，哪个部分代表主机号，例如 IP 地址，掩码有四个八位字节。如果掩码的给定位是 1，则 IP 地址的相应位是网络内部分，如果掩码的给定位是 0，则 IP 地址的相应位是主机部分。

**CIDR:**
无类域间路由使用斜杠(/)符号来指定带有 IPv4 地址的掩码。给出的地址为 x.y.z.t/n，其中 x.y.z.t 是 IP 地址，n 是默认掩码中的 1。
**网络地址:**
网络的第一个地址是网络地址。它是通过将掩码与 IP 地址(均为二进制形式)相加而获得的。另一种方法是将 IP 地址的最后 32-n 位设置为 0。
**广播地址:**
网络的最后一个地址是广播地址。它是通过将补码掩码与 IP 地址(均为二进制形式)进行“或”运算获得的。另一种方法是将 IP 地址的最后 32-n 位设置为 1。
**类:**
地址的类由地址的第一个字节来标识。目前有五个类 A、B、C、D 和 e。每个类的第一个字节的范围是:

```
Class A: 0 - 127
Class B: 128 - 191
Class C: 192 - 223
Class D: 224 - 239
Class E: 240 - 255 
```

**示例-1:**

```
CIDR: 192.168.32.1/24(x.y.z.t/n)
IP Address(Binary):  11000000101010000010000000000001
Default Mask(Binary):  11111111111111111111111100000000
Default Mask: 255.255.255.0

32-n=32-24=8  

First Address: Set last 8 bits of IP address to 0
              = 11000000101010000010000000000000
              = 192.168.32.0

Last Address: Set last 8 bits of IP address to 1
              = 11000000101010000010000011111111
              = 192.168.32.255  
```

**示例-2:**

```
CIDR: 205.15.37.39/28(x.y.z.t/n)
IP Address(Binary):  11001101000011110010010100100111
Default Mask(Binary):  11111111111111111111111111110000
Default Mask: 255.255.255.240

32-n=32-28=4  

First Address: Set last 4 bits of IP address to 0
              = 11001101000011110010010100100000
              = 205.15.37.32

Last Address: Set last 4 bits of IP address to 1
              = 11001101000011110010010100101111
              = 205.15.37.47 
```

**实现:**
下面的代码使用了上面提到的概念:

## C++

```
#include <iostream>
#include <string.h>
#include <stack>
#include <vector>
#include <math.h>

using namespace std;
    // Converts IP address to the binary form
vector<int> bina(vector<string> str)
    {
    vector<int> re(32,0);
        int a, b, c, d, i, rem;
        a = b = c = d = 1;
        stack<int> st;

        // Separate each number of the IP address

            a = stoi(str[0]);
            b = stoi(str[1]);
            c = stoi(str[2]);
            d = stoi(str[3]);

        // convert first number to binary
        for (i = 0; i <= 7; i++)
        {
            rem = a % 2;
            st.push(rem);
            a = a / 2;
        }

        // Obtain First octet
        for (i = 0; i <= 7; i++) {
            re[i] = st.top();
            st.pop();
        }

        // convert second number to binary
        for (i = 8; i <= 15; i++) {
            rem = b % 2;
            st.push(rem);
            b = b / 2;
        }

        // Obtain Second octet
        for (i = 8; i <= 15; i++) {
            re[i] = st.top();
            st.pop();
        }

        // convert Third number to binary
        for (i = 16; i <= 23; i++) {
            rem = c % 2;
            st.push(rem);
            c = c / 2;
        }

        // Obtain Third octet
        for (i = 16; i <= 23; i++) {
            re[i] = st.top();
            st.pop();
        }

        // convert fourth number to binary
        for (i = 24; i <= 31; i++) {
            rem = d % 2;
            st.push(rem);
            d = d / 2;
        }

        // Obtain Fourth octet
        for (i = 24; i <= 31; i++) {
            re[i] = st.top();
            st.pop();
        }

        return (re);
    }

    // cls returns class of given IP address
char cls(vector<string> str)
    {
        int a = stoi(str[0]);
        if (a >= 0 && a <= 127)
            return ('A');
        else if (a >= 128 && a <= 191)
            return ('B');
        else if (a >= 192 && a <= 223)
            return ('C');
        else if (a >= 224 && a <= 239)
            return ('D');
        else
            return ('E');
    }

    // Converts IP address
    // from binary to decimal form
vector<int> deci(vector<int> bi)
    {

        vector<int> arr(4,0);
        int a, b, c, d, i, j;
        a = b = c = d = 0;
        j = 7;

        for (i = 0; i < 8; i++) {

            a = a + (int)(pow(2, j)) * bi[i];
            j--;
        }

        j = 7;
        for (i = 8; i < 16; i++) {

            b = b + bi[i] * (int)(pow(2, j));
            j--;
        }

        j = 7;
        for (i = 16; i < 24; i++) {

            c = c + bi[i] * (int)(pow(2, j));
            j--;
        }

        j = 7;
        for (i = 24; i < 32; i++) {

            d = d + bi[i] * (int)(pow(2, j));
            j--;
        }

        arr[0] = a;
        arr[1] = b;
        arr[2] = c;
        arr[3] = d;
        return arr;
    }

int main()
    {

        string ipr = "192.168.1.1/24";

        // You can take user input here
        // instead of using default address
        // Ask user to enter IP address of form(x.y.z.t/n)
        cout<<"IP address CIDR format is:"<< ipr;

        // Separate IP address and n
        string str1 = "";
        int idx = 0;
        int len = ipr.size();
        len -= 3;
        while(len--){
            str1 += ipr[idx];
            idx++;
        }
        cout<<endl;
        cout<<"IP Address : " <<str1<<endl;

        string str2 = "";
        idx++;
        str2 += ipr[idx];
        idx++;
        str2 += ipr[idx];
        cout<<"Value of n : "<< str2<<endl;
        // IP address
        string tr = str1;

        // Split IP address into 4 subparts x, y, z, t
        //str = tr.split("\\.");
        vector<string> str;

        string temp;
        int n = tr.size();
        for(int i = 0; i < n; i++){
            if(tr[i] >= 48 && tr[i] <= 57)
                temp +=tr[i];
            else{
                str.push_back(temp);
                temp = "";
            }
        }
        str.push_back(temp);
        //cout<<str[0]<<endl<<str[1]<<endl<<str[2]<<endl<<str[3]<<endl;

        vector<int> b;

        cout<<endl;

        // Convert IP address to binary form
        b = bina(str);

        n = stoi(str2);
        vector<int> ntwk(32,0);
        vector<int> brd(32,0);
        int t = 32 - n;

        // Obtanining network address
        for (int i = 0; i <= (31 - t); i++) {

            ntwk[i] = b[i];
            brd[i] = b[i];
        }

        // Set 32-n bits to 0
        for (int i = 31; i > (31 - t); i--) {

            ntwk[i] = 0;
        }

        // Obtaining Broadcast address
        // by setting 32-n bits to 1
        for (int i = 31; i > (31 - t); i--) {

            brd[i] = 1;
        }

        cout<<endl;

        // Obtaining class of Address
        char c = cls(str);
        cout<<"Class : " << c << endl;

        // Converting network address to decimal
        vector<int> nt = deci(ntwk);

        // Converting broadcast address to decimal
        vector<int> br = deci(brd);

        // Printing in dotted decimal format
        cout<<"First Address : " << nt[0] << "." <<nt[1] <<"." << nt[2] <<"." << nt[3]<<endl;

        // Printing in dotted decimal format
        cout<<"Last Address : "  <<br[0] << "." <<br[1] << "." << br[2] <<"." << br[3] << endl;

        //Printing Number of Addresses in Block
        cout<<"Total Number of Addresses :" <<br[3]-nt[3]+1<<endl;

        return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;
import java.io.*;
import java.net.*;
import java.lang.Math;

class Ip {

    // Converts IP address to the binary form
    public static int[] bina(String[] str)
    {
        int re[] = new int[32];
        int a, b, c, d, i, rem;
        a = b = c = d = 1;
        Stack<Integer> st = new Stack<Integer>();

        // Separate each number of the IP address
        if (str != null)
        {
            a = Integer.parseInt(str[0]);
            b = Integer.parseInt(str[1]);
            c = Integer.parseInt(str[2]);
            d = Integer.parseInt(str[3]);
        }

        // convert first number to binary
        for (i = 0; i <= 7; i++)
        {
            rem = a % 2;
            st.push(rem);
            a = a / 2;
        }

        // Obtain First octet
        for (i = 0; i <= 7; i++) {
            re[i] = st.pop();
        }

        // convert second number to binary
        for (i = 8; i <= 15; i++) {
            rem = b % 2;
            st.push(rem);
            b = b / 2;
        }

        // Obtain Second octet
        for (i = 8; i <= 15; i++) {
            re[i] = st.pop();
        }

        // convert Third number to binary
        for (i = 16; i <= 23; i++) {
            rem = c % 2;
            st.push(rem);
            c = c / 2;
        }

        // Obtain Third octet
        for (i = 16; i <= 23; i++) {
            re[i] = st.pop();
        }

        // convert fourth number to binary
        for (i = 24; i <= 31; i++) {
            rem = d % 2;
            st.push(rem);
            d = d / 2;
        }

        // Obtain Fourth octet
        for (i = 24; i <= 31; i++) {
            re[i] = st.pop();
        }

        return (re);
    }

    // cls returns class of given IP address
    public static char cls(String[] str)
    {
        int a = Integer.parseInt(str[0]);
        if (a >= 0 && a <= 127)
            return ('A');
        else if (a >= 128 && a <= 191)
            return ('B');
        else if (a >= 192 && a <= 223)
            return ('C');
        else if (a >= 224 && a <= 239)
            return ('D');
        else
            return ('E');
    }

    // Converts IP address
    // from binary to decimal form
    public static int[] deci(int[] bi)
    {

        int[] arr = new int[4];
        int a, b, c, d, i, j;
        a = b = c = d = 0;
        j = 7;

        for (i = 0; i < 8; i++) {

            a = a + (int)(Math.pow(2, j)) * bi[i];
            j--;
        }

        j = 7;
        for (i = 8; i < 16; i++) {

            b = b + bi[i] * (int)(Math.pow(2, j));
            j--;
        }

        j = 7;
        for (i = 16; i < 24; i++) {

            c = c + bi[i] * (int)(Math.pow(2, j));
            j--;
        }

        j = 7;
        for (i = 24; i < 32; i++) {

            d = d + bi[i] * (int)(Math.pow(2, j));
            j--;
        }

        arr[0] = a;
        arr[1] = b;
        arr[2] = c;
        arr[3] = d;
        return arr;
    }

    public static void main(String args[])
    {

        int i;
        String[] str = new String[4];
        String ipr = "192.168.1.1/24";

        // You can take user input here
        // instead of using default address
        // Ask user to enter IP address of form(x.y.z.t/n)
        System.out.println("IP address CIDR format is:" + ipr);

        // Separate IP address and n
        String[] str1 = ipr.split("/");

        // IP address
        String tr = str1[0];

        // Split IP address into 4 subparts x, y, z, t
        str = tr.split("\\.");

        int[] b = new int[32];

        System.out.println();

        // Convert IP address to binary form
        b = bina(str);

        int n = Integer.parseInt(str1[1]);
        int[] ntwk = new int[32];
        int[] brd = new int[32];
        int t = 32 - n;

        // Obtanining network address
        for (i = 0; i <= (31 - t); i++) {

            ntwk[i] = b[i];
            brd[i] = b[i];
        }

        // Set 32-n bits to 0
        for (i = 31; i > (31 - t); i--) {

            ntwk[i] = 0;
        }

        // Obtaining Broadcast address
        // by setting 32-n bits to 1
        for (i = 31; i > (31 - t); i--) {

            brd[i] = 1;
        }

        System.out.println();

        // Obtaining class of Address
        char c = cls(str);
        System.out.println("Class : " + c);

        // Converting network address to decimal
        int[] nt = deci(ntwk);

        // Converting broadcast address to decimal
        int[] br = deci(brd);

        // Printing in dotted decimal format
        System.out.println("Network Address : " + nt[0]
                     + "." + nt[1] + "." + nt[2] + "." + nt[3]);

        // Printing in dotted decimal format
        System.out.println("Broadcast Address : "
                     + br[0] + "." + br[1] + "." + br[2] + "." + br[3]);
    }
}
```

**输出:**

```
IP address CIDR format is:192.168.1.1/24

Class : C
Network Address : 192.168.1.0
Broadcast Address : 192.168.1.255 
```