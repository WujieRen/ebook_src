# 启动Ambari Server

- 在Ambari Server主机上运行以下命令：

  ```shell
  ambari-server start
  ```

- 检查Ambari Server进程的运行状态使用命令：

  ```shell
  ambari-server status
  ```

- 停止运行Ambari Server使用命令：

  ```shell
  ambari-server stop
  ```

  > **[info] 注意**
  >
  > 如果您打算让Hive和Oozie使用现有的数据库实例，您必须在安装Hadoop集群**之前**就准备好该数据库。

  一旦Ambari Server启动，Ambari将运行一个数据库一致性检验以查找问题。如果发现了任何问题，Ambari Server将**终止启动**并展示如下信息：`DB configs consistency check failed`。Ambari会将关于数据库一致性检验的详细结果写到文件`/var/log/ambari-server/ambari-server-check-database.log`中。

  您可以通过如下选项来指定Ambari Server跳过该检查来启动：

  ```shell
  ambari-server start --skip-database-check
  ```

  如果您的数据库有问题，您可以选择跳过该检查，在您修正数据库一致性问题之前，请不要对您的集群拓补做出任何改变或执行集群升级。请联系Hortonworks Support请求援助并提供`ambari-server-check-database.log`的输出内容。

  ## 接下来的步骤

  [登录Ambari Server](../02-login-to-ambari-server/README.md)

  ## More Information

  - [让Hive使用一个新的或现有的数据库](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_using_new_and_existing_databases_hive.html)
  - [让Oozie使用现有的数据库](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_using_existing_databases_oozie.html)