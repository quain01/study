# [Ceph架构](https://github.com/sunxs1101/ceph)

Ceph是一个统一的、分布式的文件存储系统，可以提供高性能，高可靠性和高可扩展性。

- “统一”是指Ceph系统可以提供对象存储、块存储和文件系统存储三种功能
- “分布式”是指集群没有中心并且有集群规模有很好的可扩展性，节点间可以互相通信，动态实现数据的复制和分发，从而管理海量数据。 

![Ceph架构](img/ceph-architecture.png)

底层是基础存储系统RADOS（Reliable Autonomic Distributed Object Store），基于RADOS，Ceph可以提供理论上没有上限的集群规模可扩展性。 上层与Ceph集群的交互方式有：

1. RADOSGW(RADOS Gateway)是一种RESTful接口，应用程序与其通信，将对象存储在集群中。
2. RBD(RODOS Block Device)是一个完全分布式的块存储。
3. CephFS是一个分布式文件系统。
4. LIBRADOS库允许程序直接访问RADOS。

## [在Ceph上使用Hadoop](http://docs.ceph.org.cn/cephfs/hadoop/)

Ceph 文件系统可作为 Hadoop 文件系统（HDFS）的落地式替代品。

依赖关系:
- CephFS 的 Java 接口
- Hadoop 的 CephFS 插件

