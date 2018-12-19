# 为Ranger配置PostgreSQL

如果您使用Amazon RDS，请参考[**Amazon RDS Requierments**](../04-Amaz-RDS-reqirements/README.md)。

1. 在PostgreSQL主机上，安装对应的PostgreSQL连接器。

   **RHEL/CentOS/Oracle/Amazon Linux**

   ```shell
   yum install postgresql-jdbc*
   ```

   **SLES**

   ```shell
   zypper install -y postgresql-jdbc
   ```

2. 验证.jar文件已经存在Java共享目录中。

   ```shell
   ls /usr/share/java/postgresql-jdbc.jar
   ```

3. 将.jar文件的访问权限改为644。

   ```shell
   chmod 644 /usr/share/java/postgresql-jdbc.jar
   ```

4. 应该使用PostgreSQL数据库管理员创建Ranger数据库。

   下列的命令可以用于创建`rangerdba`用户并赋予其足够的权限。

   ```sql
   echo "CREATE DATABASE $dbname;" | sudo -u $postgres psql -U postgres
   echo "CREATE USER $rangerdba WITH PASSWORD '$passwd';" | sudo -u $postgres psql -U postgres
   echo "GRANT ALL PRIVILEGES ON DATABASE $dbname TO $rangerdba;" | sudo -u $postgres psql -U postgres 
   ```

   其中：

   - `$postgres`是Postgres用户
   - `$dbname`是PostgreSQL数据库的名字。

5. 基于PostgreSQL JDBC驱动.jar文件的位置，使用以下命令格式设置`jdbc/driver/path`的值。该命令必须运行于安装Ambari Server的主机上。

   ```shell
   ambari-server setup --jdbc-db={database-type} --jdbc-driver={/jdbc/driver/path}
   ```

   比如：

   ```shell
   ambari-server setup --jdbc-db=postgres --jdbc-driver=/usr/share/java/postgresql-jdbc.jar
   ```

6. 运行以下命令：

   ```shell
   export HADOOP_CLASSPATH=${HADOOP_CLASSPATH}:${JAVA_JDBC_LIBS}:/connector jar path
   ```

7. 为Ranger用户添加允许访问详细信息权限。

   - 将`listen_address='localhost'`的值更改为`listen_address='*'（'*'=any）`以监听在postgresql.conf中的所有IP。

   - 在`pg_hba.conf`文件中，对Ranger db用户和Ranger audit db用户做出如下修改。

     ![](..\..\..\..\..\image\postsql_user_edit.png)

8. 在编辑`pg_hda.conf`文件后，运行如下命令以刷新PostSQL数据库配置：

   ```shell
   sudo -u postgres /usr/bin/pg_etl -D $PGDATA reload
   ```

   比如，如果`pg_hba.conf`文件的位置在`/var/lib/pgsql/data`目录下，`$PGDATA`的值就是`/var/lib/pgsql/data`。