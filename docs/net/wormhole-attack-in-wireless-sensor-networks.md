# 无线传感器网络中的虫洞攻击

> 原文:[https://www . geesforgeks . org/虫洞-无线传感器网络攻击/](https://www.geeksforgeeks.org/wormhole-attack-in-wireless-sensor-networks/)

这是一种使用不止一个恶意节点进行的[网络层攻击](https://www.geeksforgeeks.org/basic-network-attacks-in-computer-network/)。用于执行这种攻击的节点优于普通节点，并且能够在长距离上建立更好的通信信道。这种攻击背后的想法是通过隧道将数据从一个受损节点转发到网络另一端的另一个恶意节点。因此，WSN 中的其他节点可能会被欺骗，认为它们比实际距离更近，这可能会导致路由算法出现问题。此外，受损的节点可能会对数据分组进行调整。

虫洞攻击也可以结合天坑攻击，使其更加有效。

**虫洞攻击可以分为 3 大类:**

1.  **打开虫洞:**
    在这种情况下，数据包首先从源发送到虫洞，然后由虫洞将它们传送到另一个虫洞，再由另一个虫洞将它们传送到目的地。网络中的其他节点被忽略，不用于数据传输。

*   **半开放虫洞:**
    在这种情况下，数据包从源发送到虫洞，虫洞将数据包直接传输到目的地。*   **Closed Wormhole:**
    In this case the data packets are directly transferred from the source to the destination in a single hop making them fictitious neighbours.

    **针对虫洞攻击的一些对策有:**

    1.  **Watchdog Model:**
        According to Watchdog model if some information is to be transmitted from one node to another through a middle node, then the sender node keeps a check on the middle node . If the middle node fails to send the data packet in the set time limit then it is declared as counterfeit and a new path is formulated to the destination nod. Although in this method the watchdog node is not always accurate in detecting a wormhole and can be fooled easily if the wormhole attack is combined with selective forwarding attack. Probability of getting false positives is also pretty high here.
    2.  **Delphi Technique:**
        In this method the delay per hop in a WSN is calculated and it is obvious that tunnel path will be longer than the normal path.So if delay per hop of any path is significantly greater than the average then the network is considered to be under attack. This method is not very successful if a large number of wormholes are present in the WSN as with the increase in wormholes the overall average of delay per hop will increase considerably.
    3.  **Wormhole Resistant Hybrid Technique:**
        This model is a combination of the Watchdog and the Delphi methods and overcomes their limitations. This method keeps tabs on both, the data loss and the delay per hop and is designed to detect every type of wormhole.
    4.  **Discovering Separate route Algorithm:**
        This algorithm discovers different paths between two nodes to identify a wormhole attack. It finds all the single and double hop neighbors and also most of the routes between nodes. So it is easily able to check if a node’s claim to be the shortest path to the destination is true or not.
    5.  **包装带:**
        包装带防止包的长距离传输。
        进一步分为:
        *   **(i)地理牵引–**确保数据不能在单跳中传输超过特定距离。
        *   **(ii)时间链–**设置数据包即使经过多次跳跃也能传输的总距离的界限。