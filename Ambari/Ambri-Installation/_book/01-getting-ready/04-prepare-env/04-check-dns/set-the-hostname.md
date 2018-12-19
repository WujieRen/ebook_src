# 设置主机名

1. 执行以下命令来验证主机名是否被设置：

   ```shell
   hostname -f
   ```

   该命令返回的应该是您刚设置的全限定域名。

2. 使用“hostname”命令设置您集群中每台主机的主机名。比如：

   ```shell
   hostname <fully.qualified.domain.name>
   ```