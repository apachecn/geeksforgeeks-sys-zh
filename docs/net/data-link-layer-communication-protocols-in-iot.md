# 物联网中的数据链路层通信协议

> 原文:[https://www . geesforgeks . org/data-link-layer-communication-protocol-in-IOT/](https://www.geeksforgeeks.org/data-link-layer-communication-protocols-in-iot/)

[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)使用多种通信协议为网络层提供服务。

众所周知，物联网是基于物联网的，智能设备通过发送和接收数据来相互通信。因此，使用多种网络协议(通信协议)来连接支持物联网的设备并建立通信。

一些流行的标准物联网通信协议包括:

1.  **蓝牙:**
    蓝牙是一种 PAN(个人区域网)或者是一种短程无线通信网络，用于通过该网络在连接的设备之间交换数据。它的价格非常便宜，从性能的角度来看，对于短距离是有效的。这是一个 2.4 千兆赫的网络，非常适合个人无线网络通信。它在 50m 至 150m 范围内提供 3 Mbps 的数据传输速率。如今，蓝牙几乎存在于所有智能手机中，它在与移动应用相连的可穿戴设备中得到了广泛应用。

*   **ZigBee :**
    Zigbee is similar to Bluetooth technology with 2.4Ghz frequency. It is a low power personal communication network. It is cheaper and is widely used for several applications. It is used for specific commercial and industrial applications. Its range varies from 10-100m. Mesh networking is one of the important advantages of Zigbee technology. Zigbee supports star or mesh network topology.*   **BLE (Bluetooth Low Energy) :**
    Bluetooth Low Energy is also known as Bluetooth smart which is a wireless PAN(Personal Area Network). The range is similar to that of Bluetooth but it consumes low power than Bluetooth. In 2011 BLE was introduced as Bluetooth 4.0\. BLE goes to sleep mode when there is no transmission of data. It is a low-cost networking protocol. The smartphones operating systems like android, ios, etc uses this BLE technology and provide a Bluetooth network.*   **Wi-Fi (Wireless Fidelity) :**
    WiFi is a local area network which is a wireless network there is no wired connection. It is Proposed by Wi-Fi Alliance. WiFi provides Internet access to devices within a range of 60 feet to 100 feet. It uses high-frequency radio signals for sending and receiving data. It uses the IEEE 802.11 standard. Its data rate varies from 2Mbps to 1.73Gbps. We can set up PAN (Personal Area Network) or LAN (Local Area Network) or WAN (Wide Area Network) in IoT systems. By Routing, we can increase the network area.*   **Z-Wave :**
    Z-wave technology is a wireless communication protocol that creates a wireless Mesh network. It is based on low power RF(Radio Frequency) based technology. It is mainly used for home automation applications and devices. It operates in 900 Mhz frequency bands. It is a more secure technology. It offers data transfer rates of 9.6Kbps, 40Kbps, or 100Kbps. Its range varies from 98 to 328 feet. It is low power and longer range IoT technology.

    *   **RFID (Radio-Frequency Identification) :**
    Radio Frequency Identification technology uses radiofrequency waves to transfer data between a reader and a movable item to identify and track. It does not require contact between reader and tagged item. RFID tag, RFID reader, RFID antenna are the key components of RFID technology. Tags operate depending upon their frequency bands of 13.56 and are mostly used.*   **Cellular :**
    Increased quantities of data can be sent over longer distances or range by using Cellular communications (GSM/3G/4G/5G etc). But it is very useful in sending a small quantity of data over the internet. Cellular carriers manage the infrastructure so when we use it we don’t need to worry about infrastructure costs and support costs.*   **Sigfox :**
    Sigfox is a form of wireless communications that provides low power and long-range wireless connectivity for devices. The messages are transmitted over the Sigfox global network. Sigfox provides one of the largest IoT networks. It is like Cellular network type which sets up antennas on towers. It is a Low Power Wide Area Networks (LPWAN).*   **Ethernet:**
    Ethernet is used to connect the devices in a Local Area Network (LAN) which is based on IEEE 802.3 standard. Ethernet is a LAN technology in which the devices are wired connection which provides data transfer rates as high as 100 Mbps. Choosing Ethernet for IoT ecosystem is a little bit costly in terms of setup and management.*   **NFC (Near Field Communication) :**
    NFC is an IoT which helps to connect devices. It provides short-range wireless connectivity technology but NFC transmission is slower than Bluetooth. It is based on Radio Frequency Identity (RFID) technology. It can operate in low power. It operates at 13.56 MHz frequency.*   **LPWAN (Low Power Wide Area Network) :**
    LPWAN (Low Power Wide Area Network) is a wireless wide area network technology whose range varies from 2 km to 1000 km depending on the technology. Siggfox, LoRa is the examples involve all major LPWAN technology.*   **LoRaWAN :**
    LoRaWAN(Long Range Wide Area Network) is a wide area network protocol. It is a low power consumption protocol that targets the wide-area network (WAN) applications with better security and mobility. It supports a large network with millions and millions of low power devices deployed on public networks. It is along with range bidirectional communication which has a range of more than 15 km.