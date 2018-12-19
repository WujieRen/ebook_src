# 安装后切换到Oracle数据库

## 关于该任务

在您已经执行了HDF初始化安装和升级之后，如果您想要为SAM和Schema Registry使用Oracle数据库存储，您仍可以切换为Oracle数据库。支持Oracle数据库12c和11g两个版本。

## 先决条件

您已经安装并配置了一个Oracle数据库。

## 步骤

1. 登录Ambari Server并关闭SAM或者Schama Registry。

2. 在配置界面，选择Oracle作为数据库类型并提供Oracle验证，JDBC连接信息，然后点击**Save**。

3. 在运行Ambari Server的主机的命令行中注册Oracle JDBC驱动jar：

   ```shell
   sudo ambari-server setup --jdbc-db=oracle --jdbc-driver=/usr/share/java/ojdbc.jar
   ```

4. 在安装SAM或Schema Registry的主机，将JDBC jar文件复制到以下路径，这取决于您要更新哪个组件：

   ```shell
   cp ojdbc6.jar /usr/hdf/current/registry/bootstrap/lib/.
    cp ojdbc6.jar /usr/hdf/current/streamline/bootstrap/lib/.
   ```

5. 在安装SAM或Schema Registry的主机，运行以下命令来为SAM和Schema Registry创建所需的表：

   ```shell
   export JAVA_HOME=/usr/jdk64/jdk1.8.0_112 ; source /usr/hdf/current/streamline/conf/streamline-env.sh ; /usr/hdf/current/streamline/bootstrap/bootstrap-storage.sh create
   
   export JAVA_HOME=/usr/jdk64/jdk1.8.0_112 ; source /usr/hdf/current/registry/conf/registry-env.sh ; /usr/hdf/current/registry/bootstrap/bootstrap-storage.sh create
   ```

   > **[info] 注意**
   >
   > 您只能在一台主机上运行一次该命令以准备数据库。

6. 验证在Oracle数据库中已经创建了这些新的表。

7. 在Ambari中重启SAM或Schema Registry。

8. 如果您为SAM指定了一个Oracle数据库，在您重启SAM后运行以下命令：

   ```shell
   export JAVA_HOME=/usr/jdk64/jdk1.8.0_112 ; source /usr/hdf/current/streamline/conf/streamline-env.sh ; /usr/hdf/current/streamline/bootstrap/bootstrap.sh
   ```

9. 确认Sam或Schema Registry可用，并关闭维护模式。