# 密码学和网络安全原理

> 原文:[https://www . geesforgeks . org/密码学与网络安全原理/](https://www.geeksforgeeks.org/cryptography-and-network-security-principles/)

在当今的情况下，系统的安全性是任何组织的唯一优先事项。任何组织的主要目标都是保护他们的数据免受攻击者的攻击。在[密码学](https://www.geeksforgeeks.org/computer-network-cryptography-introduction/)中，攻击有两种类型，比如[被动攻击和主动攻击](https://www.geeksforgeeks.org/difference-between-active-attack-and-passive-attack/)。

被动攻击是指在不影响系统资源的情况下从系统中检索信息，而主动攻击是指检索系统信息并对系统资源及其操作进行更改。

安全原则可分为以下几类:

1.  **Confidentiality:** 
    The degree of confidentiality determines the secrecy of the information. The principle specifies that only the sender and receiver will be able to access the information shared between them. Confidentiality compromises if an unauthorized person is able to access a message. 

    例如，让我们考虑发送方 A 想要与接收方 B 共享一些机密信息，而这些信息被攻击者 c 截获，现在这些机密信息掌握在入侵者 c 手中。

2.  **Authentication:** 
    Authentication is the mechanism to identify the user or system or the entity. It ensures the identity of the person trying to access the information. The authentication is mostly secured by using username and password. The authorized person whose identity is preregistered can prove his/her identity and can access the sensitive information. 
3.  **Integrity:** 
    Integrity gives the assurance that the information received is exact and accurate. If the content of the message is changed after the sender sends it but before reaching the intended receiver, then it is said that the integrity of the message is lost. 
4.  **Non-Repudiation:** 
    Non-repudiation is a mechanism that prevents the denial of the message content sent through a network. In some cases the sender sends the message and later denies it. But the non-repudiation does not allow the sender to refuse the receiver. 
5.  **Access control:** 
    The principle of access control is determined by role management and rule management. Role management determines who should access the data while rule management determines up to what extent one can access the data. The information displayed is dependent on the person who is accessing it. 
6.  **可用性:**
    可用性原则规定资源在任何时候都可以提供给授权方。如果信息不可访问，它就没有用。系统应该有足够的可用信息来满足用户的要求。