# 在Postgres中配置Druid和Superset元数据存储

## 关于该任务

Druid和Superset要求有相关的数据存储以存储元数据。要使用Postgres实现此功能，请安装Postgres并为Druid元数据创建一个数据库。如果您已经用MySQL创建了数据存储，您不需要在Postgres中配置额外的元数据存储。

## 步骤

1. 登录Postgres

   ```shell
   sudo su postgres
   psql
   ```

2. 创建数据库，用户和密码，他们的值都是`druid`，并为`druid`用户分配数据库权限：

   ```sql
   create database druid;
   CREATE USER druid WITH PASSWORD 'druid';
   GRANT ALL PRIVILEGES ON DATABASE  "druid" to druid;
   ```

3. 创建数据库，用户和密码，它们的孩子都是`superset`，并为用户`superset`分配数据库权限：

   ```sql
   reate database superset;
   CREATE USER superset WITH PASSWORD 'superset';
   GRANT ALL PRIVILEGES ON DATABASE "superset" to superset;
   ```
