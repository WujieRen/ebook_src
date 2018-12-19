# 为Ranger配置一个数据库实例

必须要有一个正在运行的MySQL，Oracle，PostgreSQL，或者亚马逊RDS数据库实例，以供Ranger使用。Ranger的安装将会创建两个新的用户（默认用户名：`rangeradmin`和`rangerlogger`）和两个新的数据库（默认数据库名：`ranger`和`ranger_audit`）。

您可以从下面列出的选项中做出选择：

- [为Ranger配置MySQL](./01-config-mysql-for-ranger/README.md)
- [为Ranger配置PostgreSQL](./02-config-psql-for-ranger/README.md)
- [为Ranger配置Oracle](./03-cinfig-oracle-ranger/README.md)

如果您选择使用亚马逊的RDS数据库，则有其他的要求：

- [Amazon RDS需求](./04-Amaz-RDS-reqirements/README.md)