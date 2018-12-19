# SLES 12

在一台有网络连接的服务主机上，用命令行执行下列操作。

## 步骤

1. 下载Ambari二进制文件。这会安装默认的PostgreSQL Ambari数据库。

   ```shell
   zypper install ambari-server
   ```

2. 当提示确认事务和依赖检查时，输入 `y`。

   一个成功的安装会输出类似于以下内容的结果：

   ```shell
   Retrieving package postgresql-libs-8.3.5-1.12.x86_64 (1/4), 172.0 KiB (571.0 KiB unpacked)
   Retrieving: postgresql-libs-8.3.5-1.12.x86_64.rpm [done (47.3 KiB/s)]
   Installing: postgresql-libs-8.3.5-1.12 [done]
   Retrieving package postgresql-8.3.5-1.12.x86_64 (2/4), 1.0 MiB (4.2 MiB unpacked)
   Retrieving: postgresql-8.3.5-1.12.x86_64.rpm [done (148.8 KiB/s)]
   Installing: postgresql-8.3.5-1.12 [done]
   Retrieving package postgresql-server-8.3.5-1.12.x86_64 (3/4), 3.0 MiB (12.6 MiB unpacked)
   Retrieving: postgresql-server-8.3.5-1.12.x86_64.rpm [done (452.5 KiB/s)]
   Installing: postgresql-server-8.3.5-1.12 [done]
   Updating etc/sysconfig/postgresql...
   Retrieving package ambari-server-2.7.1.0-143.noarch (4/4), 99.0 MiB (126.3 MiB unpacked)
   Retrieving: ambari-server-2.7.1.0-143.noarch.rpm [done (3.0 MiB/s)]
   Installing: ambari-server-2.7.1.0-143 [done]
    ambari-server 0:off 1:off 2:off 3:on 4:off 5:on 6:off
   ```

   > **[info] 注意**
   >
   > 当在有限制的网络访问或者无法访问网络的情况下部署集群时，您应该提供一种可选的能够访问这些数据的路径或方式。
   >
   > Ambari Server默认使用内嵌的PostgreSQL数据库。当您安装Ambari Server时，必须能够安装PostgreSQL包及其依赖。通常，这些包是可用的，而且是您操作系统仓库的一部分。请验证您已经有了合适且可用的仓库以供postgresql-server包使用。

## 接下来的步骤

[设置Ambari Server](../03-setup-the-ambari-server/README.md)

## More Information

[使用本地仓库](../../02-using-a-local-repository/README.md)