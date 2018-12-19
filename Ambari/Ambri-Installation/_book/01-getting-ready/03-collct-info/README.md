# 收集信息

在部署集群前，你应该收集以下信息：

* 在您系统中的每台主机的[全限定域名](https://baike.baidu.com/item/FQDN)。Ambari 集群安装向导支持使用IP地址。您可以使用以下命令来检查或者验证主机的全限定域名。

  ```text
  hostname -f 
  ```

> **[info] 注意**
>
> 将所有的组件部署在一台主机上是可以的，但是这仅仅限于用作初始化评估的目的。通常，设置一个最小的集群您需要至少三台主机，一个主节点和两个从节点。

* 一个安装清单，该清单列出了您分别想要在每台主机上安装的组件。
* 要用做存储挂载点的基本目录：
  * NameNode data
  * DataNodes data
  * Secondary NameNode data
  * Oozie data
  * YARN data
  * Zookeeper data，如果您要安装Zookeeper
  * 各种 log，pid，以及 db 文件，这取决于您的安装类型。

> **[warning] 警告**
>
> 您必须使用为您的组件和Hadoop数据提供持久化存储的基目录。将组建安装在那些可能会被主机删除的位置很可能会导致集群崩溃或者数据丢失。比如：在基目录路径中不要使用`/tmp` 。

