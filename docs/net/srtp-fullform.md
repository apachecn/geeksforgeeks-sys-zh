# SRTP 全模

> 原文:[https://www.geeksforgeeks.org/srtp-fullform/](https://www.geeksforgeeks.org/srtp-fullform/)

SRTP 代表**安全实时传输协议**是一种实时传输协议，它为 RTP 数据提供了更多功能，例如加密、身份验证、完整性，以及针对重放攻击或拒绝服务(DoS)攻击的屏蔽。它拦截实时传输协议数据包，然后将等效的 s RTP 数据包转发到发送端。此外，它还拦截 SRTP 数据包，并将等效的实时传输协议数据包转发给接收端。

**功能:**

*   Authentication, encryption and other functions are optional and can be enabled or disabled as needed.
*   It uses [Advanced Encryption Standard (AES)](https://www.geeksforgeeks.org/aes-full-form/) as the default password for encryption and decryption.
*   It provides appropriate protection for the heterogeneous environment composed of wired or wireless connections.
*   It provides the confidentiality of RTP payload.
*   It is independent of the transport layer, network layer and physical layer used by RTP.
*   SRTP uses two types of keys: a session key for providing password conversion and a master key for deriving the session key in a password-secure manner.

**优势:**

*   It can easily accommodate new encryption algorithms.
*   It is safe for unicast and multicast RTP applications.
*   Resulting in high throughput and low packet expansion.
*   Its bandwidth and computing cost are very low.
*   There is a high tolerance for packet loss and reordering.

**缺点:**

*   Only the payload of RTP packet is encrypted, and the RTP extension header is not encrypted.
*   Only used for commercial applications, which is difficult for ordinary consumers to access.
*   In the case of multi-party conference, selective forwarding mixer (SFM) is needed to optimize a small number of real-time transport protocol parameters when forwarding a part of the stream. It acts as an intermediary to destroy the end-to-end security between peer systems.