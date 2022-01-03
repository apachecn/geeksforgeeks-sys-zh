# 加密、加密算法及其未来

> 原文:[https://www . geeksforgeeks . org/encryption-its-algorithms-and-its-future/](https://www.geeksforgeeks.org/encryption-its-algorithms-and-its-future/)

**密码学中的加密**是一个过程，通过该过程，纯文本或一条信息被转换成密文或只能由信息的接收者解码的文本。用于加密过程的算法称为密码。它有助于保护消费者信息、电子邮件和其他敏感数据免受未经授权的访问，并保护通信网络。目前有许多选择，并找出最安全的算法，满足我们的要求。有四种这样的加密算法是高度安全且不可破解的。

*   **Triple DES:** Triple DES is a block cipher algorithm that was created to replace its older version Data Encryption Standard(DES). In 1956 it was found out that 56 key-bit of DES was not enough to prevent brute force attack, so Triple DES was discovered with the purpose of enlarging the key space without any requirement to change algorithm. It has a key length of 168 bits three 56-bit DES keys but due to meet-in-middle-attack the effective security is only provided for only 112 bits. However Triple DES suffers from slow performance in software. Triple DES is well suited for hardware implementation. But presently Triple DES is largely replaced by AES (Advance Encryption Standard).
*   **[RSA](https://www.geeksforgeeks.org/rsa-algorithm-cryptography/) :**

    RSA 是一种非对称密钥算法，以其创造者 Rivest、Shamir 和 Adleman 的名字命名。该算法是基于大合成数的因子很难的事实:当整数是素数时，这种方法被称为素数分解。它是公钥和私钥的生成器。我们使用公钥将明文转换为密文，私钥用于将密文转换为明文。每个人都可以使用公钥，而私钥是保密的。公钥和私钥保持不同。从而使其成为更加安全的数据安全算法。

*   **Twofish:**

    Twofish 算法是 blowfish 算法的继承。它是由布鲁斯·施奈尔、约翰·凯斯利、怀汀、戴维·瓦格纳、克里斯·霍尔和尼尔斯·福格森设计的。它使用块加密。它使用一个长度为 256 位的密钥，据说对运行在较小处理器(如智能卡)上的软件和嵌入硬件都很有效。它允许实现者在加密速度、密钥设置时间和代码大小之间进行权衡，以平衡性能。由布鲁斯·施奈尔的 Counterpane Systems 设计，Twofish 是非专利的，没有许可证，可以免费使用。

*   **[AES](https://www.geeksforgeeks.org/difference-between-aes-and-des-ciphers/):**

    高级加密标准也简称 AES，是美国政府为保护重要信息而选择的对称分组密码，用于加密硬件和软件的敏感数据。AES 有三个大小分别为 128、192 和 256 位的 128 位固定分组密码。密钥大小不受限制，但块大小最大为 256 位。AES 设计基于置换网络，不使用数据加密标准网络。

**未来工作:**
随着技术的进步，加密数据变得更加容易，利用神经网络，保护数据安全变得更加容易。谷歌大脑的神经网络已经开发出了创建加密的方法，但没有教授加密算法的细节。数据科学家和密码学家正在寻找方法来防止对加密算法的暴力攻击，以避免对敏感数据的任何未经授权的访问。