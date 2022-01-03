# 确定 IPv4 地址的类别、网络和主机标识的程序

> 原文:[https://www . geesforgeks . org/program-decision-class-network-host-id-IP v4-address/](https://www.geeksforgeeks.org/program-determine-class-network-host-id-ipv4-address/)

给定一个字符串形式的有效 IPv4 地址，它遵循[类全](https://www.geeksforgeeks.org/ip-addressing-introduction-and-classful-addressing/)寻址。任务是确定给定 IPv4 地址的类别，并从中分离网络和主机标识部分。

**示例:**

```
Input : 1.4.5.5
Output :
Given IP address belongs to Class A
Network ID is 1
Host ID is 4.5.5

Input : 130.45.151.154
Output :
Given IP address belongs to Class B
Network ID is 130.45
Host ID is 151.154
```

**接近**

1.  **确定类别:**思路是检查 IP 地址的第一个八位字节。众所周知，对于等级 **A** 第一个八位字节的范围为**1–126**，对于等级 **B** 第一个八位字节的范围为**128–191**，对于等级 **C** 第一个八位字节的范围为 **192- 223** ，对于等级 **D** 第一个八位字节的范围为**224–239**

2.  **确定网络和主机 ID:** 我们知道[子网掩码](https://www.iplocation.net/subnet-mask)对于类 **A** 为 **8** ，对于类 **B** 为 **16** ，对于类 **C** 为 **24** ，而类 **D** 和 **E** 不划分网络和主机 ID。
    对于第二个示例，第一个八位字节是 130。所以，它属于乙类**。B 类的子网掩码为 16。因此，前 16 位或前两个八位字节是网络标识部分，其余是主机标识部分。
    因此，网络标识为 **130.45** ，主机标识为 **151.154****

## **C**

```
// C program to determine class, Network
// and Host ID of an IPv4 address
#include<stdio.h>
#include<string.h>

// Function to find out the Class
char findClass(char str[])
{
    // storing first octet in arr[] variable
    char arr[4];
    int i = 0;
    while (str[i] != '.')
    {
        arr[i] = str[i];
        i++;
    }
    i--;

    // converting str[] variable into number for
    // comparison
    int ip = 0, j = 1;
    while (i >= 0)
    {
        ip = ip + (str[i] - '0') * j;
        j = j * 10;
        i--;
    }

    // Class A
    if (ip >=1 && ip <= 126)
        return 'A';

    // Class B
    else if (ip >= 128 && ip <= 191)
        return 'B';

    // Class C
    else if (ip >= 192 && ip <= 223)
        return 'C';

    // Class D
    else if (ip >= 224 && ip <= 239)
        return 'D';

    // Class E
    else
        return 'E';
}

// Function to separate Network ID as well as
// Host ID and print them
void separate(char str[], char ipClass)
{
    // Initializing network and host array to NULL
    char network[12], host[12];
    for (int k = 0; k < 12; k++)
        network[k] = host[k] = '\0';

    // for class A, only first octet is Network ID
    // and rest are Host ID
    if (ipClass == 'A')
    {
        int i = 0, j = 0;
        while (str[j] != '.')
            network[i++] = str[j++];
        i = 0;
        j++;
        while (str[j] != '\0')
            host[i++] = str[j++];
        printf("Network ID is %s\n", network);
        printf("Host ID is %s\n", host);
    }

    // for class B, first two octet are Network ID
    // and rest are Host ID
    else if (ipClass == 'B')
    {
        int i = 0, j = 0, dotCount = 0;

        // storing in network[] up to 2nd dot
        // dotCount keeps track of number of
        // dots or octets passed
        while (dotCount < 2)
        {
            network[i++] = str[j++];
            if (str[j] == '.')
                dotCount++;
        }
        i = 0;
        j++;

        while (str[j] != '\0')
            host[i++] = str[j++];

        printf("Network ID is %s\n", network);
        printf("Host ID is %s\n", host);
    }

    // for class C, first three octet are Network ID
    // and rest are Host ID
    else if (ipClass == 'C')
    {
        int i = 0, j = 0, dotCount = 0;

        // storing in network[] up to 3rd dot
        // dotCount keeps track of number of
        // dots or octets passed
        while (dotCount < 3)
        {
            network[i++] = str[j++];
            if (str[j] == '.')
                dotCount++;
        }

        i = 0;
        j++;

        while (str[j] != '\0')
            host[i++] = str[j++];

        printf("Network ID is %s\n", network);
        printf("Host ID is %s\n", host);
    }

    // Class D and E are not divided in Network
    // and Host ID
    else
        printf("In this Class, IP address is not"
           " divided into Network and Host ID\n");
}

// Driver function is to test above function
int main()
{
    char str[] = "192.226.12.11";
    char ipClass = findClass(str);
    printf("Given IP address belongs to Class %c\n",
                                           ipClass);
    separate(str, ipClass);
    return 0;
}
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to determine class, Network
// and Host ID of an IPv4 address

class NetworkId{
    static String findClass(String str){
        // Calculating first occurrence of '.' in str
        int index = str.indexOf('.');
        // First octate in str in decimal form
        String ipsub = str.substring(0,index);
        int ip = Integer.parseInt(ipsub);
        // Class A
        if (ip>=1 && ip<=126)
            return "A";
        // Class B
        else if (ip>=128 && ip<=191)
            return "B";
        // Class C
        else if (ip>=192 && ip<223)
            return "C";
        // Class D
        else if (ip >=224 && ip<=239)
            return "D";
        // Class E
        else
            return "E";
    }

    static void separate(String str, String ipClass){
        // Initializing network and host empty
        String network = "", host = "";

        if(ipClass == "A"){
            int index = str.indexOf('.');
            network = str.substring(0,index);
            host = str.substring(index+1,str.length());
        }else if(ipClass == "B"){
            //Position of breaking network and HOST id
            int index = -1;
            int dot = 2;
            for(int i=0;i<str.length();i++){
                if(str.charAt(i)=='.'){
                    dot -=1;
                    if(dot==0){
                        index = i;
                        break;
                    }
                }
            }
            network = str.substring(0,index);
            host = str.substring(index+1,str.length());
        }else if(ipClass == "C"){
            //Position of breaking network and HOST id
            int index = -1;
            int dot = 3;
            for(int i=0;i<str.length();i++){
                if(str.charAt(i)=='.'){
                    dot -=1;
                    if(dot==0){
                        index = i;
                        break;                    
                    }
                }
            }
            network = str.substring(0,index);
            host = str.substring(index+1,str.length());
        }else if(ipClass == "D" || ipClass == "E"){
            System.out.println("In this Class, IP address"+
            " is not divided into Network and Host IDs");
            return;
        }
        System.out.println("Network ID is "+network);
        System.out.println("Host ID is "+host);
    }
    public static void main(String[] args) {
        String str = "192.226.12.11";
        String ipClass = findClass(str);
        System.out.println("Given IP address belings to Class "+ipClass);
        separate(str,ipClass);
    }
}
```

## **蟒蛇 3**

```
#function to determine the class of an Ip address
def findClass(ip):
  if(ip[0] >= 0 and ip[0] <= 127):
    return "A"

  elif(ip[0] >=128 and ip[0] <= 191):
    return "B"

  elif(ip[0] >= 192 and ip[0] <= 223):
    return "C"

  elif(ip[0] >= 224 and ip[0] <= 239):
    return "D"

  else:
    return "E"

#function to separate network and host id from the given ip address
def seperate(ip, className):

  #for class A network
  if(className == "A"):
    print("Network Address is : ", ip[0])
    print("Host Address is : ", ".".join(ip[1:4]))

  #for class B network
  elif(className == "B"):
    print("Network Address is : ", ".".join(ip[0:2]))
    print("Host Address is : ", ".".join(ip[2:4]))

  #for class C network
  elif(className == "C"):
    print("Network Address is : ", ".".join(ip[0:3]))
    print("Host Address is : ", ip[3])

  else:
    print("In this Class, IP address is not divided into Network and Host ID")

#driver's code
if __name__ == "__main__":

  ip = "192.226.12.11"
  ip = ip.split(".")
  ip = [int(i) for i in ip]

  #getting the network class
  networkClass = findClass(ip)
  print("Given IP address belongs to class : ", networkClass)

  #printing network and host id
  ip = [str(i) for i in ip]
  separate(ip, networkClass)
```

****输出:****

```
Given IP address belongs to Class C
Network ID is 192.226.12
Host ID is 11
```

**本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**