# Oracle先决条件

由于**Amazon RDS的限制**【此处要添加超链接】，Ranger数据库用户和表空间必须手动创建，且要手动为Ranger数据库用户赋予所需的权限。

1. 从master用户账户（在RDS数据库实例创建时被创建）登录RDS Oracle Server并执行以下命令：

   ```sql
   create user $rangerdbuser identified by “password”;
   GRANT CREATE SESSION,CREATE PROCEDURE,CREATE TABLE,CREATE VIEW,CREATE SEQUENCE,CREATE PUBLIC SYNONYM,CREATE ANY SYNONYM,CREATE TRIGGER,UNLIMITED Tablespace TO $rangerdbuser;
   create tablespace $rangerdb datafile size 10M autoextend on;
   alter user $rangerdbuser DEFAULT Tablespace $rangerdb;
   ```

   其中，`$rangerdb`是一个真实的Ranger数据库用户名（比如：ranger），`$rangerdbuser`是Ranger数据库用户名（比如：rangeradmin）。

2. 如果您使用的是Ranger KMS，执行以下命令：

   ```sql
   create user $rangerdbuser identified by “password”;
   GRANT CREATE SESSION,CREATE PROCEDURE,CREATE TABLE,CREATE VIEW,CREATE SEQUENCE,CREATE PUBLIC SYNONYM,CREATE ANY SYNONYM,CREATE TRIGGER,UNLIMITED Tablespace TO $rangerkmsuser;
   create tablespace $rangerkmsdb datafile size 10M autoextend on;
   alter user $rangerkmsuser DEFAULT Tablespace $rangerkmsdb;
   ```

   其中，`$rangerkmsdb`是一个真实的Ranger数据库名（比如：rangerkms），`$rangerkmsuser`是一个Ranger数据库用户名（比如：rangerkms）。