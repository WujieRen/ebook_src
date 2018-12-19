# Ubuntu 16

在一台有网络连接的服务主机上，用命令行执行下列操作。

## 步骤

1. 用`root`用户登录您的主机。

2. 将Ambari仓库文件下载到您的安装主机上。

   ```shell
   wget -O /etc/apt/sources.list.d/ambari.list http://public-repo-1.hortonworks.com/ambari/ubuntu16/2.x/updates/2.7.1.0/ambari.list
   ```

   ```shell
   apt-key adv --recv-keys --keyserver keyserver.ubuntu.com B9733A7A07513CAD
   ```

   ```shell
   apt-get update
   ```

   > **[warning] 警告**
   >
   > 不要改动文件名`ambari.list`。因为在Ambari Agent注册时，要求Ambari Server主机上的该文件（ambari.repo）可用。

3. 通过检查包名列表确认Ambari已经被成功下载。

   ```shell
   apt-cache showpkg ambari-server
   ```

   ```shell
   apt-cache showpkg ambari-agent
   ```

   ```shell
   apt-cache showpkg ambari-metrics-assembly
   ```

   在列表中看到Ambari包说明安装成功。

   > **[info] 注意**
   >
   > 当在有限的网络访问或者无法访问网络的情况下部署集群时，您应该提供一种可选的能够访问这些数据的路径或方式。
   >
   > Ambari Server默认使用内嵌的PostgreSQL数据库。当您安装Ambari Server时，必须能够安装PostgreSQL包及其依赖。通常，这些包是可用的，而且是您操作系统仓库的一部分。请验证您已经有了合适且可用的仓库以供postgresql-server包使用。

   ## 接下来的步骤

   - [安装Ambari Server](../02-install-the-ambari-server/README.md)
   - [设置Ambari Server](../03-setup-the-ambari-server/README.md)

   ## More Information

   [使用本地仓库](../../02-using-a-local-repository/README.md)

