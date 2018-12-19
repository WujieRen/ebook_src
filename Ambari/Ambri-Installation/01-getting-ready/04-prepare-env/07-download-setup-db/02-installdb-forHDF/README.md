# 为HDF服务安装数据库

在安装Schema Registry，SAM，Druid和Superset时，需要一个关系数据库来存储元数据。您可以从MySQL，Postgres，Oracle，或者MariaDB中任选一个。该主题描述的是如何去安装MySQL，Postgres，Oracle以及如何为SAM和Schema Registry创建数据库。如果您正使用Superset在一个现有的HDP集群上安装，您可以跳过该安装说明，因为MySQL已经随Druid一起安装了。在这种情况下，配置数据库即可。

> **[info] 注意**
>
> 您需要安装Postgres，或Oracle，或MySQL；不必都安装。推荐您使用MySQL。

<br/>
> **[warning] 警告**
>
> 如果您安装Postgres，您必须安装Postgres 9.5或者更高的版本以供SAM和Schema Registry使用。Ambari默认不安装Postgres 9.5，所以您必须手动安装。

## 安装并配置MySQL

- [安装MySQL](./install-mysql.md)
- [在MySQL中配置SAM和Schema Registry元数据存储](./config-sam-schema-in-mysql.md)
- [在MySQL中配置Druid和Superset元数据存储](./config-druid-superset-mysql.md)

## 安装并配置Postgres

- [安装Postgres](./install-postgres.md)
- [配置Postgres以允许远程连接](./allow-postgres-remote-connection.md)
- [在Postgres中配置SAM和Schema Registry](./config-sam-schema-in-postgres.md)
- [在Postgres中配置Druid和Superset元数据存储](./config-druid-superset-postgres.md)

## 使用Oracle数据库

- [这部分叫“指定一个Oracle数据库供SAM和Schema Registry使用”](./specify-oracle.md)
- [这部分叫“在安装后切换到Oracle数据库”](./switch-oracle-after-installe.md)