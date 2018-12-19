# 为Ranger配置MySQL

## 先决条件

当时用MySQL时，用于Ranger管理策略存储表的存储引擎**必须**支持事务。InnoDB就是一个例子，它支持事务的引擎。不支持事务的引擎不适合作为策略存储

## 步骤

如果您使用Amazon RDS，请参阅[**Amazon RDS Requirements**](../04-Amaz-RDS-reqirements/README.md)。

1. 应该使用MySQL数据库管理员创建Ranger数据库。

   下面的命令可以用于创建用户`rangerdba`，密码为`rangerdba`。

   ​	a. 用root用户登录，然后使用以下命令创建`rangerdba`用户并赋予该用户足够的权限。	

   ```sql
   CREATE USER 'rangerdba'@'localhost' IDENTIFIED BY 'rangerdba';
   
   GRANT ALL PRIVILEGES ON *.* TO 'rangerdba'@'localhost';
   
   CREATE USER 'rangerdba'@'%' IDENTIFIED BY 'rangerdba';
   
   GRANT ALL PRIVILEGES ON *.* TO 'rangerdba'@'%';
   
   GRANT ALL PRIVILEGES ON *.* TO 'rangerdba'@'localhost' WITH GRANT OPTION;
   
   GRANT ALL PRIVILEGES ON *.* TO 'rangerdba'@'%' WITH GRANT OPTION;
   
   FLUSH PRIVILEGES;
   ```

   ​	b. 用`exit`命令退出MySQL。

   ​	c. 现在，您应该能用以下命令以`rangerdba`用户连接数据库。

   ​	   `mysql -u rangerdba -prangerdba`

   ​	   在用`rangerdba`特使登录后，使用`exit`命令退出MtSQL。

2. 使用以下命令验证`mysql-connector-java.jar`放在了Java共享目录下。该命令必须运行于安装Ambari Server的主机上。

   ```shell
   ls /usr/share/java/mysql-connector-java.jar
   ```

   如果在Java共享目录中没有该文件，使用以下命令去安装MySQL连接.jar文件。

   **RHEL/CentOS/Oracle/Amazon Linux**

   ```shell
   yum install mysql-connector-java*
   ```

   **SLES**

   ```shell
   zypper install mysql-connector-java*
   ```

3. 基于MySQLJDBC驱动.jar文件的路径，使用以下命令格式设置`jdbc/driver/path`的值。该命令必须在安装Ambari Server的主机上运行。

   ```shell
   ambari-server setup --jdbc-db={database-type} --jdbc-driver={/jdbc/driver/path}
   ```

   比如：

   ```shell
   ambari-server setup --jdbc-db=mysql --jdbc-driver=/ust/share/java/mysql-connector-java.jar
   ```
