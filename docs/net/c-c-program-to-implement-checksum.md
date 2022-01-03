# 实现校验和的 C/C++程序

> 原文:[https://www . geesforgeks . org/c-c-程序到实现-校验和/](https://www.geeksforgeeks.org/c-c-program-to-implement-checksum/)

[校验和](https://www.geeksforgeeks.org/error-detection-code-checksum/)是一种错误检测方法，用于在数据/消息从发送方传输到接收方时检测数据/消息中的错误。该方法由更高层协议使用，并利用发送端的校验和生成器和接收端的校验和检查器。

**示例:**

> **输入:**send _ message =“10101111”，rec_message =“10101101”，block_size = 8
> **输出:**错误
> **解释:**由于 send _ message 和 rec _ message 中的第 7 位不同，最终校验和值不等于零，表示传输过程中出现了一些错误。
> 
> **输入:**send _ message =“10000101100011100101001101101101”，rec _ message =“100001011000111001010011101101”，block_size = 8
> **输出:**无错误

**方法:**给定的问题可以分为以下两部分:

*   生成**发件人信息**的[校验和](https://www.geeksforgeeks.org/error-detection-in-computer-networks/)值可以通过以下步骤完成:
    *   将消息分成给定的**块大小**的[二进制字符串](https://www.geeksforgeeks.org/tag/binary-string/)。
    *   所有的[二进制串加在一起](https://www.geeksforgeeks.org/program-to-add-two-binary-strings/)得到**和**。
    *   代表**和**的二进制字符串的[补码是所需的校验和值。](https://www.geeksforgeeks.org/1s-2s-complement-binary-number/)
*   检查**收到的消息**(即**rec _ message+senders _ checksum**)的值是否等于 **0** 。
    *   接收消息的校验和可以类似于上述过程中计算的校验和来计算。
    *   如果校验和值为 **0** ，则消息传输正常，没有错误，否则，传输过程中出现了一些错误。

下面是上述方法的实现:

## C++

```
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the One's complement
// of the given binary string
string Ones_complement(string data)
{
    for (int i = 0; i < data.length(); i++) {
        if (data[i] == '0')
            data[i] = '1';
        else
            data[i] = '0';
    }

    return data;
}

// Function to return the checksum value of
// the give string when divided in K size blocks
string checkSum(string data, int block_size)
{
    // Check data size is divisible by block_size
    // Otherwise add '0' front of the data
    int n = data.length();
    if (n % block_size != 0) {
        int pad_size = block_size - (n % block_size);
        for (int i = 0; i < pad_size; i++) {
            data = '0' + data;
        }
    }

    // Binary addition of all blocks with carry
    string result = "";

    // First block of data stored in result variable
    for (int i = 0; i < block_size; i++) {
        result += data[i];
    }

    // Loop to calculate the block
    // wise addition of data
    for (int i = block_size; i < n; i += block_size) {

        // Stores the data of the next bloack
        string next_block = "";

        for (int j = i; j < i + block_size; j++) {
            next_block += data[j];
        }

        // Stores the binary addition of two blocks
        string additions = "";
        int sum = 0, carry = 0;

        // Loop to calculate the binary addition of
        // the current two blocls of k size
        for (int k = block_size - 1; k >= 0; k--) {
            sum += (next_block[k] - '0')
                   + (result[k] - '0');
            carry = sum / 2;
            if (sum == 0) {
                additions = '0' + additions;
                sum = carry;
            }
            else if (sum == 1) {
                additions = '1' + additions;
                sum = carry;
            }
            else if (sum == 2) {
                additions = '0' + additions;
                sum = carry;
            }
            else {
                additions = '1' + additions;
                sum = carry;
            }
        }

        // After binary add of two blocks with carry,
        // if carry is 1 then apply binary addition
        string final = "";

        if (carry == 1) {
            for (int l = additions.length() - 1; l >= 0;
                 l--) {
                if (carry == 0) {
                    final = additions[l] + final;
                }
                else if (((additions[l] - '0') + carry) % 2
                         == 0) {
                    final = "0" + final;
                    carry = 1;
                }
                else {
                    final = "1" + final;
                    carry = 0;
                }
            }

            result = final;
        }
        else {
            result = additions;
        }
    }

    // Return One's complements of result value
    // which represents the required checksum value
    return Ones_complement(result);
}

// Function to check if the received message
// is same as the senders message
bool checker(string sent_message,
             string rec_message,
             int block_size)
{

    // Checksum Value of the senders message
    string sender_checksum
        = checkSum(sent_message, block_size);

    // Checksum value for the receivers message
    string receiver_checksum = checkSum(
        rec_message + sender_checksum, block_size);

    // If receivers checksum value is 0
    if (count(receiver_checksum.begin(),
              receiver_checksum.end(), '0')
        == block_size) {
        return true;
    }
    else {
        return false;
    }
}

// Driver Code
int main()
{
    string sent_message
        = "10000101011000111001010011101101";
    string recv_message
        = "10000101011000111001010011101101";
    int block_size = 8;

    if (checker(sent_message,
                recv_message,
                block_size)) {
        cout << "No Error";
    }
    else {
        cout << "Error";
    }

    return 0;
}
```

**Output**

```
No Error
```

***时间复杂度:** O(N)*
***辅助空间:** O(block_size)*