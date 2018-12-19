# Debian 9

在一台有网络连接的服务主机上，用命令行执行下列操作。

## 步骤

1. 安装Ambari二进制文件。这会安装默认的PostgreSQL Ambari数据库。

   ```
   apt-get install ambari-server
   ```

   > **[info] 注意**
   >
   > 当在有限制的网络访问或者无法访问网络的情况下部署集群时，您应该提供一种可选的能够访问这些数据的路径或方式。
   >
   > Ambari Server默认使用内嵌的PostgreSQL数据库。当您安装Ambari Server时，必须能够安装PostgreSQL包及其依赖。通常，这些包是可用的，而且是您操作系统仓库的一部分。请验证您已经有了合适且可用的仓库以供postgresql-server包使用。

## 接下来的步骤

[设置AmbariServer](../03-setup-the-ambari-server/README.md)

## More Information

[使用本地仓库](../../02-using-a-local-repository/README.md)