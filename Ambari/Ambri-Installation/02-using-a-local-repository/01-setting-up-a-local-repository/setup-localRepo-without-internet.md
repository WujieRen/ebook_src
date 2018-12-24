# 没有网络访问时设置本地仓库

## 先决条件

您必须已经完成了[开始设置本地仓库](./prepare-localRepo.md)的过程。

--

要完成本地仓库的设置，请完成以下操作：

## 步骤

1. 为您所想要创建的仓库获取压缩磁盘存档文件（tarball）。

2. 复制仓库包文件到web服务器目录，并解压该存档文件：

   a. 进入您创建的web服务器目录。

   **对于REHL/CentOS/Oracle/Amazon Linux：**

   ```shell
   cd /var/www/html
   ```

   **对于SLES：**

   ```shell
   cd /srv/www/htdocs/rpms
   ```

   **对于Debian/Ubuntu：**

   ```shell
   cd /var/www/html
   ```

   b. 解压仓库包文件并将其移至下面的位置，&lt;web.server&gt;，&lt;web.server.directory&gt;，&lt;OS&gt;，&lt;version&gt;和&lt;latest.version&gt;分别代表了web服务器的名字，web服务器家目录，操作系统类型，版本，和最近的发布版本。分别如下：

   **Ambari仓库**

   解压Ambari仓库包到&lt;web.server.directory&gt;目录下。

   **HDF堆栈仓库**

   创建目录&lt;web.server.directory&gt;/hdf，并将HDF仓库包解压到&lt;web.server.directory&gt;/hdf目录下。

   **HDP堆栈仓库**

   创建目录&lt;web.server.directory&gt;/hdp，并将HDP仓库包解压到&lt;web.server.directory&gt;/hdp目录下。

3. 验证您可以在浏览器中访问刚刚创建的本地仓库，仓库地址中的&lt;web.server&gt;，&lt;web.server.directory&gt;，&lt;OS&gt;，&lt;version&gt;，和&lt;latest.version&gt;分别代表服务器的名字，web服务器家目录，操作系统类型，版本和最近的发行版本。分别如下：

   **Ambari基URL**

   http://<web.server&gt;/Ambari-2.7.1.0/<OS&gt;

   **HDF基URL**

   http://<web.server&gt;/hdf/HDF/<OS&gt;/3.x/updates/<latest.version&gt;

   **HDP基URL**

   http://<web.server&gt;/hdp/HDP/<OS&gt;/3.x/updates/<latest.version&gt;

   **HDP-UTILS基URL**

   http://<web.server&gt;/hdp/HDP-UTILS-<version&gt;/repos/<OS&gt;

   > **[warning] 警告**
   >
   > 一定要记录这些基URL。您将在安装Ambari和集群时用到它们。

4. 可选：如果在您的环境中配置了多个仓库，请在您集群的所有节点上部署以下插件。

   a. **对于RHEL/CentOS/Oracle7：**

   b. 编辑`/etc/yum/plugincoonf.d/priorities.conf`文件，添加以下内容：

   ```shell
   [main]
   ```

   ```shell
   enabled=1
   ```

   ```shell
   gpgcheck=0
   ```

## More Information

[获取公共仓库](../../03-obtaining-public-repositories/README.md)

