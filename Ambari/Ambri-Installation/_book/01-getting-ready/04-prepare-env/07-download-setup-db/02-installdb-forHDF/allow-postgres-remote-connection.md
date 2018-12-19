# 配置Postgres允许远程连接

## 关于该任务

在您部署集群之前，配置Postgres以允许远程连接是非常重要的。如果您在安装集群之前没有执行这些操作，安装将会失败。

## 步骤

1. 打开文件并更新以下内容：

   ```text
   # "local" is for Unix domain socket connections only
   local all all trust
   
   
   # IPv4 local connections:
   host all all 0.0.0.0/0 trust
   
   
   # IPv6 local connections:
   host all all ::/0 trust
   ```

2. 打开文件更新以下内容：

   ```text
   listen_addresses = '*'
   ```

3. 重启Postgres：

   ```shell
   systemctl stop postgresql-9.6.service
   systemctl start postgresql-9.6.service 
   ```
