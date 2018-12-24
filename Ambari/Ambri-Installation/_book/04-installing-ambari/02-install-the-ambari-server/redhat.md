# RHEL/CentOS/Oracle Linux 7

在一台有网络连接的服务主机上，用命令行执行下列操作。

## 步骤

1. 下载Ambari二进制文件。这会安装默认的PostgreSQL Ambari数据库。

   ```shell
   yum install ambari-server
   ```

2. 当提示确认事务和依赖检查时，输入 `y`。

   一个成功的安装会输出类似于以下内容的结果：

   ```shell
   Installing : postgresql-libs-9.2.18-1.el7.x86_64         1/4
   Installing : postgresql-9.2.18-1.el7.x86_64              2/4
   Installing : postgresql-server-9.2.18-1.el7.x86_64       3/4
   Installing : ambari-server-2.7.1.0-143.x86_64           4/4
   Verifying  : ambari-server-2.7.1.0-143.x86_64           1/4
   Verifying  : postgresql-9.2.18-1.el7.x86_64              2/4
   Verifying  : postgresql-server-9.2.18-1.el7.x86_64       3/4
   Verifying  : postgresql-libs-9.2.18-1.el7.x86_64         4/4
   
   Installed:
     ambari-server.x86_64 0:2.7.1.0-143
   Dependency Installed:
    postgresql.x86_64 0:9.2.18-1.el7
    postgresql-libs.x86_64 0:9.2.18-1.el7
    postgresql-server.x86_64 0:9.2.18-1.el7
   Complete!
   ```

   > **[info] 注意**
   >
   > 请同意关于信任Hortonworks GPG密匙的警告。该密匙将被自动下载并被用于验证来自Hortonworks的包。您将看到如下信息：
   >
   > `Importing GPG key 0x07513CAD: Userid: "Jenkins (HDP Builds) <jenkin@hortonworks.com>" From : http://s3.amazonaws.com/dev.hortonworks.com/ambari/centos7/RPM-GPG-KEY/RPM-GPG-KEY-Jenkins`

> **[info] 注意**
>
> 当在有限制的网络访问或者无法访问网络的情况下部署集群时，您应该提供一种可选的能够访问这些二进制文件的路径或方式。
>
>    Ambari Server默认使用内嵌的PostgreSQL数据库。当您安装Ambari Server时，必须能够安装PostgreSQL包及其依赖。通常，这些包是可用的，而且是您操作系统仓库的一部分。请验证您已经有了合适且可用的仓库以供postgresql-server包使用。

## 接下来的步骤

[设置Ambari Server](../03-setup-the-ambari-server/README.md)

## More Information

[使用本地仓库](../../02-using-a-local-repository/README.md)