# 卡珊德拉的告密者

> 原文:[https://www.geeksforgeeks.org/snitches-in-cassandra/](https://www.geeksforgeeks.org/snitches-in-cassandra/)

在本文中，我们将讨论飞贼及其类型，并了解如何配置 cassandra-topology.properties 和 cassandra-rackdc.properties 文件来帮助配置数据中心和集群。

**告密者:**
**中的卡珊德拉告密者**非常有用，告密者还有助于记录，以避免在同一个机架上存储多个数据副本。在 Cassandra 中，避免多个副本是非常重要的方面。在复制策略中，我们分配了副本的数量，并定义了数据中心。这些信息对飞贼识别节点和哪个机架非常有帮助。

在[卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)中，告密者的工作是确定它应该使用哪些数据中心和机架来读取数据和写入数据。在卡珊德拉中，默认情况下所有飞贼都是动态的。

**告密者类型:**

1.  **简单飞贼:**
    在卡珊德拉中，它是默认飞贼，对开发环境有好处。它不知道数据中心或机架，也不寻找 Cassandra-topology . properties 文件，因此不能用于多数据中心环境。

2.  **GossipingPropertyFileSnitch:** 
    In Cassandra, it is very important file snitch also recommends by datastax for production usage. This snitch also look for the Cassandra-topologies.properties file to identify the cluster information such that which data center and rack belong to then we configure in the cassandra-rackdc.properties file to the rest of the nodes using gossip. 

    我们可以通过编辑 Cassandra-topologies . properties 文件来配置 GossipingPropertyFileSnitch。
    我们来看看。

```
dc=DC1
rack=RACK1
prefer_local=true 
```

1.  这里，我们使用的 dc 和 rack 指的是数据中心和机架，而 prefer _ local = true 指的是在多个数据中心不通信时与本地 IP 地址通信，以限制网络带宽的使用。

2.  **Ec2Snitch:** 
    It is important snitch for deployments and it is a simple snitch for Amazon EC2 deployments where all nodes are in a single region. In Ec2Snitch region name refers to data center and availability zone refers to rack in a cluster. 
3.  **Ec2MultiRegionSnitch:** 
    In Cassandra, this snitch we use where the clusters span multiple regions and Ec2MultiRegionSnitch for Amazon EC2-based clusters. 
4.  **GoogleCloudSnitch:** 
    In Cassandra, it is the snitch for a Cassandra deployment on the Google Cloud Platform (GCP) across a single or multiple regions. It is the snitch which supports GCP (Google Cloud Plateform). 
5.  **RackInferringSnitch:** 
    In this snitch we find out the location by rack and datacenter. In this snitch the 3rd and 4th octets of IP address for example 10.40.08.230 corresponds to rack and datacenter. This is very useful snitch for writing custom snitch classes. 
6.  **PropertyFileSnitch:** 
    This snitch uses the cassandra-topology.properties file and we must define the nodes information by which we can Determines the closeness of the nodes. 
    We can identify nodes information based on the datacenter and rack which they belong to. To determine the closeness of the nodes The PropertyFileSnitch used the network definitions from the cassandra-topology.properties file. 
7.  **CloudstackSnitch:** 
    It is the snitch which based on cloud and It is snitch for an Apache Cloudstack-based cluster. 

现在，让我们了解一下 cassandra-topology.properties 和 cassandra-rackdc.properties 文件。

**了解卡珊德拉拓扑属性和卡珊德拉 rackdc 属性文件:**

它包含整个集群的拓扑以及 cassandra-topology.properties 和 cassandra-rackdc.properties 文件的信息。
举个例子。

```
dc = DC1
rack = RAC1 
rack= RAC2
```

在下面给出的示例中，DC1 和 DC2 是两个物理数据中心，每个数据中心有两个机架。在 Cassandra 中，properties filesnitch 使用属性文件(即 Cassandra-topics . properties 文件)来标识集群的节点。如果我们在 Cassandra-topology . properties 文件中没有识别出集群的节点，那么数据库就认为数据在默认的数据中心和机架中。

```
# datacenter One
10.40.08.230  = DC1:RAC1
10.30.11.231  = DC1:RAC1
10.54.06.232  = DC1:RAC1

130.40.20.106  = DC1:RAC2
130.41.21.229  = DC1:RAC2
130.42.29.111  = DC1:RAC2

# datacenter Two

100.46.12.120  = DC2:RAC1
100.60.13.201  = DC2:RAC1
100.24.35.184  = DC2:RAC1

30.22.20.110  = DC2:RAC2
30.35.21.210  = DC2:RAC2
30.27.20.231  = DC2:RAC2 
```

当我们要在集群中添加或删除节点时，更新 Cassandra-topics . properties 文件非常重要，这样可以知道节点属于哪个数据中心和机架。从性能角度来看，向卡珊德拉记录信息非常重要。

在这里，我们将描述 cassandra-rackdc.properties 文件:在上面给出的例子中，我们使用了节点的以下信息。
我们来看看。

```
dc=DC1
rack=RAC1 
```

**注意:**
有以下飞贼类型查找 cassandra-rackdc.properties 文件以识别节点集群信息，例如哪个数据中心和哪个机架属于哪个。
我们来看看。

```
GossipingPropertyFileSnitch
Ec2Snitch
Ec2MultiRegionSnitch 
```