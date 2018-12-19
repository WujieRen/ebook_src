# 在Postgres中配置SAM和Schema并注册元数据

## 关于该任务

如果您已经安装了MySQL，并使用MySQL为SAM和Schema Registry配置了元数据存储，您不需要在Postgres中为它们配置额外的元数据存储。

## 步骤

1. 登录Postgres：

   ```shell
   sudo su postgres
   psql
   ```

2. 创建一个密码为`regisrey`的数据库：

   ```shell
   create database registry;
   CREATE USER registry WITH PASSWORD 'registry';
   GRANT ALL PRIVILEGES ON DATABASE "registry" to registry;
   ```

3. 创建一个密码为`streamline`的数据库：

   ```shell
   create database streamline;
   CREATE USER streamline WITH PASSWORD 'streamline';
   GRANT ALL PRIVILEGES ON DATABASE "streamline" to streamline;
   ```