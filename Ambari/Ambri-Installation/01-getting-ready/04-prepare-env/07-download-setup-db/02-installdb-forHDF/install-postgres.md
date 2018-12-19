# 安装Postgres

## 在您开始之前

如果您已经安装了MySQL数据库，您可以跳过这些步骤。

> **[warning] 警告**
>
> 您必须安装Postgres9.5或者更高版本为SAM和Schema Registry使用。Ambari不安装Postgres 9.5，所以您必须手动安装Postgres。

## 步骤

1. 根据您操作系统的要求安装Red Hat包管理器（RPM）：

   ```shell
   yum install https://yum.postgresql.org/9.6/redhat/rhel-7-x86_64/pgdg-redhat96-9.6-3.noarch.rpm
   ```

2. 安装Postgres 9.5或更高版本：

   ```shell
   yum install postgresql96-server postgresql96-contrib postgresql96
   ```

3. 初始化数据库：

   - 对于CentOS 7，使用以下语法：

     ```shell
     /usr/pgsql-9.6/bin/postgresql96-setup initdb
     ```

   - 对于CentOS 6，使用以下语法：

     ```shell
     sudo service postgresql initdb
     ```

4. 开启Postgres：

   比如，如果您使用的是CentOS 7，使用以下语法：

   ```shell
   systemctl enable postgresql-9.6.service
   systemctl start postgresql-9.6.service
   ```

5. 验证您是否可以登录：

   ```shell
   sudo su postgres
   psql
   ```
