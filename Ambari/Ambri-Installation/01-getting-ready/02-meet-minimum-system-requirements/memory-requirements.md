# 内存要求

Ambari主机应该有至少1G的RAM，并且有500MB是空闲的。

在任何主机上检查其可用内存，运行：

`free-m`

如果您计划在您的集群上安装Ambari 度量服务（Ambari Metrics Service，AMS），则应查看在 Hortonworks 数据平台 Apache Ambari 操作手册中使用的 Ambari Metrics 标准，以获取关于资源要求的指南。一般来说，根据集群的规模，你计划去运行 Ambari Metrics Collector 的主机应该有至少如下的可用内存和磁盘空间：

| 主机数目 | 可用内存 | 磁盘空间 |
| :--- | :--- | :--- |
| 1 | 1024 MB | 10 GB |
| 10 | 1024 MB | 20 GB |
| 50 | 2048 MB | 50 GB |
| 100 | 4096 MB | 100 GB |
| 300 | 4096 MB | 100 GB |
| 500 | 8096 MB | 200 GB |
| 1000 | 12288 MB | 200 GB |
| 2000 | 16348 MB | 500 GB |

> **[info] 注意**
>
> 使用这些值作为指导。一定要针对您特定的环境去测试它们。

