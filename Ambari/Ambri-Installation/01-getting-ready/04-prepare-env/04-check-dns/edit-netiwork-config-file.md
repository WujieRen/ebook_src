# 编辑网络配置文件

1. 使用文本编辑器打开在每台主机上的配置网络配置文件，并为每台主机设置所需的网络配置。比如：

   ```shell
   vi /etc/sysconfig/network
   ```

2. 编辑HOSTNAME属性以设置全限定域名。

   ```shell
   NETWORKING=yes
   ```

   ```shell
   HOSTNAME=<fully.qualified.domain.name>
   ```