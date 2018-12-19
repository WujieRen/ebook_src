# Amazon Linux 2

在一台有网络连接的主机上，使用命令行执行以下操作。

## 步骤

1. 用`root`用户登录您的主机。

2. 将Ambari仓库文件下载到您的安装主机上。

   ```shell
   wget -nv http://public-repo-1.hortonworks.com/ambari/amazonlinux2/2.x/updates/2.7.1.0/ambari.repo -O /etc/yum.repos.d/ambari.repo
   ```

   > **[info] 注意**
   >
   > 不要改动文件名`ambari.repo`。因为在Ambari Agent注册时，要求Ambari Server主机上的该文件（ambari.repo）可用。

3. 通过检查仓库列表验证仓库是否已被配置成功。

   ```shell
   yum repolist
   ```

   在控制台展示的列表中，针对Ambari存储库如果可以看到有类似于以下结果的值，说明配置成功。

   ```shell
   repo id                    repo name                                       status
   ambari-2.7.1.0-143        ambari Version - ambari-2.7.1.0-143            12
   epel/x86_64                Extra Packages for Enterprise Linux 7 - x86_64  11,387
   ...
    repolist: 30,578
   ```

   版本可能会有不同，这取决于您安装的版本。

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
