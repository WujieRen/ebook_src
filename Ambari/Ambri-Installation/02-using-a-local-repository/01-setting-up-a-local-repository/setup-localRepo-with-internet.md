# 有临时访问的网络时设置本地仓库

## 先决条件

您必须已经完成了[开始设置本地仓库](./prepare-localRepo.md)的过程。

--

要完成本地仓库的设置，请完成以下操作：

## 步骤

1. 为主机上的Ambari和堆栈安装仓库配置文件

2. 验证仓库可用性；

   **对于RHEL，CentOS，Oracle，或者Amazon Linux**

   ```shell
   yum repolist
   ```

   **对于SLES**

   ```shell
   zypper repos
   ```

   **对于Debian和Ubuntu**

   ```shell
   dpkg-list
   ```

3. 同步仓库目录到您的镜像服务器：

   - 浏览web服务器目录：

     **对于RHEL，CentOs，Oracle或者Amazon Linux:**

     ```shell
     cd /var/www/html
     ```

     **对于SLES:**

     ```shell
     cd /srv/www/html/htdocs/rpms
     ```

     **对于Debian和Ubuntu：**

     ```shell
     cd /var/www/html
     ```

   - 为Ambari创建`ambari`目录和同步仓库：

     ```shell
     mkdir -p ambari/<OS>
     ```

     ```shell
     cd ambari/<OS>
     ```

     ```shell
     reposync -r HDP-<latest.version>
     ```

     ```shell
     reposync -r HDP-UTILS-<version>
     ```

   - 为Hortonworks数据平台（HDP）堆栈仓库创建`hdp`目录和同步仓库：

     ```shell
     mkdir -p hdp/<OS>
     ```

     ```shell
     cd hdp
     ```

     ```shell
     reposync -r HDP-<latest.version>
     ```

     ```shell
     reposync -r HDP-UTILS-<version>
     ```

   - 为HDF堆栈仓库创建`hdf`目录和同步仓库。

     ```shell
     mkdir -p hdf/<OS>
     ```

     ```shell
     cd hdf/<OS>
     ```

     ```shell
     reposync -r HDF-<latest.version>
     ```

4. 生成仓库元数据：

   **对于Ambari：**

   ```shell
   createrepo <web.server.directory>/ambari/<OS>/Update-Ambari-2.7.1.0
   ```

   **对于HDP堆栈仓库：**

   ```shell
   createrepo <web.server.directory>/hdp/<OS>/HDP-<latest.version>
   ```

   ```shell
   createrepo <web.server.directory>/hdp/<OS>/HDP-UTILS-<version>
   ```

   **对于HDF堆栈仓库：**

   ```shell
   createrepo <web.server.directory>/hdf/<OS>/HDF-<latest.version>
   ```

5. 验证您可以在浏览器中访问刚刚创建的仓库：

    **Ambari基URL**

    http://<web.server&gt;/ambari/<OS&gt;/Updates-Ambari-2.7.1.0

    **HDF基URL**

    http://<web.server&gt;/hdf/<OS&gt;/HDF-<latest.version&gt;

    **HDP基URL**

    http://<web.server&gt;/hdp/<OS&gt;/HDP-<latest.version&gt;

    **HDP-UTILS基URL**

    http://<web.server&gt;/hdp/<OS&gt;/HDP-UTILS-<version&gt;

   以上的URL解释：

   - <web.server&gt;——web服务器主机的全限定域名

   - <version&gt;——Hortonworks堆栈版本号

   - <OS&gt;——centos7，sles12，ubuntu14，ubuntu16，ubuntu18，或者ubuntu19

> **[warning] 警告**
>
> 一定要记录这些基URL。您将会在安装Ambari和集群的时候送到它们。

6. 可选：如果在您的环境中有多个仓库配置，请在您集群的所有节点上部署以下插件。

   a. 安装插件。

   **对于RHEL/CentOS/Oracle 7：**

   ```shell
   yum install yum-plugin-priorities
   ```

   b. 编辑`/etc/yum/pluginconf.d/priorities.conf`文件，添加以下内容：

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