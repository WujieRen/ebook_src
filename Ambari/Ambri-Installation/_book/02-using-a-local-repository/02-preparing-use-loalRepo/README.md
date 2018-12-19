# 准备Ambari仓库配置文件以使用本地仓库

## 步骤

1. 从公共仓库下载文件`ambari.repo`：

   ```text
   http://public-repo-1.hortonworks.com/ambari/<OS>/2.x/updates/2.7.1.0/ambari.repo
   ```

   <OS&gt;——centos7，sles12，ubuntu14，ubuntu16，ubuntu18，或者debian9。

2. 编辑文件`ambari.repo`并替换文件中的Ambari基URL为您在设置本地仓库时获取的`baseurl`。

   ```shell
   [Updates-Ambari-2.7.1.0]
   ```

   ```shell
   name=Ambari-2.7.1.0-Updates
   ```

   ```shell
   baseurl=INSERT-BASE-URL
   ```

   ```shell
   gpgcheck=1
   ```

   ```shell
   gpgkey=http://public-repo-1.hortonworks.com/ambari/centos7/RPM-GPG-KEY/RPM-GPG-KEY-Jenkins
   ```

   ```shell
   enabled=1
   ```

   ```shell
   priority=1
   ```

   > **[info] 注意**
   >
   > 您可以通过设置`gpgcheck=0`来禁用GPG检查。或者您也可以保留检查，但是请将`gpgkey`的URL改为您本地仓库中的GPG-KEY地址。

   **本地仓库中的基URL**

   - 使用仓库tar包构建（没有网络连接）

     http://<web.server&gt;/Ambari-2.7.1.0/<OS&gt;

   - 使用仓库文件固件（临时可访问网络）

     http://<web.server&gt;/ambari/<OS&gt;/Updates-Ambari-2.7.1.0

   以上URL中，<web.server&gt;=FQDN指的是web server所在的主机，<OS&gt;指的是amazonlinux2，centos7，sles12，ubuntu14，ubuntu16，ubuntu18，或者debian9。

3. 将`ambari.repo`文件放置在您打算安装Ambari Server的主机上：

   **对于RHEL/CentOS/Amazon Linux**

   ```shell
   /etc/yum.repos.d/ambari.repo
   ```

   **对于SLES**

   ```text
   /etc/zypp/repos.d/ambari.repo
   ```

   **对于Debian/Ubuntu**

   ```text
   /etc/apt/sources.list.d/ambari.list
   ```

4. 编辑文件`/etc/yum/pluginconf.d/priorities.conf`，添加以下内容：

   ```text
   [main]
   ```

   ```text
   enabled=1
   ```

   ```text
   gpgcheck=0
   ```

## 下一步

进行操作[安装Ambri](../../04-installing-ambari/README.md)以安装并设置Ambari Server。

## More Information

[没有网络连接时设置本地仓库](../01-setting-up-a-local-repository/setup-localRepo-without-internet.md)

[有临时网络连接时设置本地仓库](../01-setting-up-a-local-repository/setup-localRepo-with-internet.md)