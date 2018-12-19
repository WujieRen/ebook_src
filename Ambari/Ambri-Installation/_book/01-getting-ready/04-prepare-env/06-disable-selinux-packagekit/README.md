# 禁用SELinux和PackageKit并检查umask值

1. 为了使Ambari设置能够正常运行，您必须禁用SELinux。在集群中的每台主机上输入：

   ```shell
   setenforce 0
   ```

   > **[info] 注意**
   >
   > 为了能够永久禁用SELinux，请设置`/etc/selinux/config` 文件中的属性SELNIUX=disabled。这将确保在您重启机器后，SELinux也不会自动启动。

2. 在一台安装了PackageKit，运行着RHEL/CentOS的主机上，用文本编辑器打开文件`/etc/yum/pluginconf.d/refresh-packagekit.conf`。做出如下配置：

   ```shell
   enabled=0
   ```

   > **[info] 注意**
   >
   > 在Debian、SLES、或者Ubuntu系统上，默认不开启PackageKit。在安装Debian、SLES、或者Ubuntu的系统上，您可以跳过该步骤——如果您没有指定开启PackageKit。

3. 在Linux系统上，UMASK（用户掩码或用户文件创建掩码）指定了当一个新的文件或者新的文件夹被创建时被授予的默认权限，或基权限。大多数Linux发行版都将umask的默认值设为022。umask值为022表示授予了新创建的文件或者文件夹的读、写、以及执行权限为755。umask值为027则表示授予新创建的文件或文件夹的读、写、以及执行权限为750。

   Ambari，HDP，和HDF支持的umask值为022（这和0022在功能上是相同的），027（和0027相同）。在所有主机上的umask值必须设置为支持的值。

   **UMASK值设置举例**

   为当前登录的session设置umask值：

   ```shell
   umask 022
   ```

   检查当前值：

   ```shell
   umask
   ```

   为所有交互用户永久改变umask值：

   ```shell
   echo umask 0022 >> /etc/profile
   ```