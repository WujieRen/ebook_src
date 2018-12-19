# 安装MySQL

## 关于该任务

您可以安装MySQL5.5或更高版本。

## 在安装之前

在Ambari主机上，为MySQL安装JDBC驱动，然后将其添加到Ambari：

```shell
yum install mysql-connector-java* \
sudo ambari-server setup --jdbc-db=mysql \
--jdbc-driver=/usr/share/java/mysql-connector-java.jar
```

## 步骤

1. 在您想要安装MySQL元数据以供SAM，Scheme注册，和Druid使用的节点上登录。

2. 安装MySQL和MySQL Community Server，并启动MySQL服务：

   ```shell
   yum localinstall \
   https://dev.mysql.com/get/mysql57-community-release-el7-8.noarch.rpm
   
   yum install mysql-community-server
   
   systemctl start mysqld.service
   ```

3. 获取随机生成的MySQL root用户密码：

   ```shell
   grep 'A temporary password is generated for root@localhost' \
   /var/log/mysqld.log | tail -1
   ```

4. 重设MySQL root用户账户的密码。输入下列命令。系统将提示您输入在上一步中获取的密码。MySQL随后会要求您更改密码。

   ```shell
   /usr/bin/mysql_secure_installation
   ```
