# PostgreSQL先决条件

在Amazon RDS PostgreSQL Server上的Ranger数据库用户应该在安装Ranger之前被创建，而且该角色必须被赋予能够创建数据库的权限。

1. 使用master用户账户，从master用户账户登录Amazon RDS PostgreSQL（在RDS PostgreSQL实例创建时被创建）并执行以下命令：

   ​	a. `CREATE USER $rangerdbuser WITH LOGIN PASSWORD 'password'`

   ​	b. `GRANT *$rangerdbuser* to *$postgresroot*`

   其中`$postgresroot`是RDS PostgreSQL主用户账户（比如：postgresroot）`$rangerdbuser`是Ranger数据库用户名（比如：rangeradmin）。

2. 如果您使用的是Ranger KMS，执行下列命令：

   ​	a. `CREATE USER *$rangerkmsuser* WITH LOGIN PASSWORD '*password*'`

   ​	b. `GRANT *$rangerkmsuser* to *$postgresroot*`

   其中`$postgresroot`是RDS PostgreSQL主用户账户（比如：postgresroot）`$rangerkmsuser`是Ranger KMS用户名（比如：rangerkms）。