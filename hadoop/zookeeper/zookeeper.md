[TOC]



### 一.zookeeper概述?

- hadoop整个生态圈都是各种动物,zookeeper的图标像不像一个动物园铲屎官~

<img src="C:\Users\35110\AppData\Roaming\Typora\typora-user-images\image-20200107083322029.png" alt="image-20200107083322029" style="zoom: 50%;" align="left"/>

- Apache ZooKeeper是一个[分布式](https://baike.baidu.com/item/分布式/19276232)的，开放源码的[分布式应用程序](https://baike.baidu.com/item/分布式应用程序/9854429)协调服务，是[Google](https://baike.baidu.com/item/Google)的Chubby一个[开源](https://baike.baidu.com/item/开源/246339)的实现，是Hadoop和Hbase,Spark的重要组件。它是一个为分布式应用提供一致性服务的软件，提供的功能包括：配置维护、域名服务、分布式同步、组服务等。



### 二.zookeeper结构

1. Zookeeper的结构是一个树状结构，每一个节点称之为Znode节点,  节点的路径必须是唯一的,  起始节点是/;  (有点类似于Linux文件系统);
2. Zookeeper不存在相对路径，所有的路径都必须从根节点开始计算;
3. 要求每一个节点都必须携带数据;
4. 任意一个持久节点下都可以挂载子节点，但是临时节点不能有子节点;
5. Znode树维系在内存以及磁盘中;
   1. 在磁盘中的目的是为了持久存储
   2. 在内存中的目的是为了查询快
6. 理论上，Zookeeper可以作为缓存服务器使用，但是实际过程中不这么做。Zookeeper是为了集群的管理和协调设计的，如果存储大量数据耗费内存，导致协调的效率降低;
7. 在Zookeeper中，会对每一次的写操作（create/delete/rmr/set）进行自动的编号，编号是全局递增的，这个编号称之为是事务id - Zxid - 事务id是用十六进制表示;

### 三.zookeeper命令

| 命令                                          | 解释                 |
| --------------------------------------------- | -------------------- |
| ls /                                          | 查看指定节点的子节点 |
| create /nodes  'nodes data'                   | 创建节点             |
| delete /nodes                                 | 删除节点nodes        |
| rmr /nodes                                    | 递归删除nodes        |
| set /nodes 'nodes data2'                      | 修改数据             |
| get /nodes                                    | 获取数据             |
| create -e /nodes/linshi '临时节点数据'        | 创建临时节点         |
| create -s /shunxu/a/b/c/d  '创建多级顺序节点' | 创建顺序节点         |



### 四.zookeeper 节点信息

 

dasda

dsadad

qedqwd