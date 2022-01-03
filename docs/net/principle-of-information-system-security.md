# 信息系统安全原理

> 原文:[https://www . geesforgeks . org/information-principle-system-security/](https://www.geeksforgeeks.org/principle-of-information-system-security/)

**信息[系统安全](https://www.geeksforgeeks.org/system-security/)** 或**信息安全**是指对计算机、网络和相关数据提供保护的过程。随着技术的出现，信息在广域网上存储得越多，保护信息免受未经授权者滥用就变得越重要。每个组织都有包含其活动机密信息的数据集。

为信息系统提供安全性的主要原因不仅仅是一个方面，而是三个方面:

```
1. Confidentiality
2. Integrity
3. Availability 
```

这些层级共同构成了中情局三角**，这恰好是保护信息系统安全的首要需要。这三个层次证明了信息系统安全的**原则。****

**让我们一个接一个地经历同样的事情:**

1.  ****Confidentiality:**
    The main essence of this feature lies in the fact that only the authorized personnel should be allowed the access to the data and system. The unauthorised individuals must be kept away from the information. This is ensured by checking the **authorisation** of every individual who tries to access the database.

    例如，一个组织的行政部门不得获取员工的私人信息。** 
2.  ****完整性:**
    当所呈现的数据未被触及或者更确切地说，未被任何未授权的力量改变时，完整性得到了保证。因此，闭上眼睛就可以查阅信息。信息的完整性可能会以无意或有意的方式被改变。有意地，任何个人都可以通过恶意内容传递信息。相反，任何被授权的个人可能会无意中妨碍信息，例如，他可能会删除信息的任何特定重要部分。**
3.  ****可用性:**
    此功能意味着任何授权人员都可以在给定的**时间范围内访问和修改信息。**这里需要注意的一点是，信息的可及性有限。每个组织访问它的时间范围是不同的。**

****平衡信息安全和访问:**
组织的唯一目的是**保护用户的利益**，并在必要时向他们提供适当数量的信息。此外，与此同时，有必要为信息提供足够的安全性**，以便任何人都无法访问。保持信息安全和可访问性之间完美平衡的需要源于信息安全永远不可能是绝对的这一事实。****

****提供对一条信息的免费访问是有害的，并且很难限制任何可访问性。因此，我们需要确保保持所需的精确平衡，以便用户和安全专业人员都感到满意。****

******信息安全工具:**
有各种工具可供各种组织使用，以确保最大限度的信息系统安全。然而，这些工具并不能保证绝对的安全性，但是如上所述，有助于形成信息访问和安全性之间的关键平衡。****

****让我们逐一研究这些工具:****

1.  ******Authentication:**
    This is the foremost important tool that needs to be kept in mind before starting the crucial process of ensuring security. The process of authentication is when the system identifies someone with one or more than one factors. These factors must be unique for most of the users. For example, ID and password combinations, face recognition, thumb impression etc.

    这些因素并不总是可信的，因为一个人可能会失去它们，或者任何局外人都可能会接触到它们。对于这些情况，可以使用**多因素授权**，这是通过组合上述因素中的任意两个或多个来完成的。**** 
2.  ******访问控制:**
    在确保正确的个人能够访问信息后，必须确保只有适当的信息才能到达他或她手中。通过使用访问控制工具，系统判断哪个用户必须能够读取或写入或修改某些信息。为此，它通常维护所有用户的列表。可以找到两种类型列表:

    *   **访问控制列表(ACL)**–这只是有资格访问信息的个人列表
    *   **基于角色的访问控制列表(RBAC)**–该列表包括授权人员的姓名以及他们各自被授权对信息执行的操作。**** 
3.  ******加密:**
    有时信息通过互联网传输，因此任何人访问它的风险增加，现在工具必须强大才能避免。在这种情况下，任何人都可以轻松访问和修改信息。为了避免这种情况，一个新的工具，加密，投入使用。使用加密技术，可以将机密信息放入难以解密的不可读字符中，只有信息的授权接收者才能轻松读取。****