# 为Ranger配置Oracle

如果您 使用的是Amazon RDS，请参考[**Amazon RDS requirements**](../04-Amaz-RDS-reqirements/README.md)。

1. 在Oracle主机上，安装合适版本的JDBC .jar文件

   - 从<http://www.oracle.com/technetwork/database/features/jdbc/index-091264.html>下载Oracle JDBC（OJDBC）驱动。

   - 对于**Oracle Database 11g:**选择Oracle Database 11g Release 2 drivers > ojdbc6.jar。

   - 对于**Oracle Database 12c:**选择Oracle Database 12c Release 1 drivers > ojdbc7.jar。

   - 将.jar文件复制到Java共享目录。比如：

     `cp ojdbc.jar /usr/share/java`

     > **[info] 注意**
     >
     > 确保.jar文件有合适的权限。比如：
     >
     > `chmod 644 /usr/share/java/ojdbc7.jar`

2. 应该是会用Oracle数据管理员创建Ranger数据库。

   下面的一系列命令可以用来创建`RANGERDBA`用户，并使用SQL*Plus（Oracle数据库管理工具）为期赋予权限：

   ```
   # sqlplus sys/root as sysdba
   CREATE USER $RANGERDBA IDENTIFIED BY $RANGERDBAPASSWORD;
   GRANT SELECT_CATALOG_ROLE TO $RANGERDBA;
   GRANT CONNECT, RESOURCE TO $RANGERDBA;
   QUIT;
   ```

3. 使基于Oracle JDBC驱动.jar文件的位置，使用以下命令格式设置`jdbc/driver/path`的值。该命令必须运行于安装Ambari Server的主机上。

   ```shell
   ambari-server setup --jdbc-db={database-type} --jdbc-driver={/jdbc/driver/path}
   ```

   比如：

   ```shell
   ambari-server setup --jdbc-db={database-type} --jdbc-driver=/usr/share/java/ojdbc6.jar
   ```