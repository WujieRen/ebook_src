# 在MySQL中配置Druid和Superset元数据存储

## 关于该任务

Druid和Superset要求有相关的数据存储以存储元数据。要为此使用MySQL，请安装MySQL并未Druid元数据创建数据库。

## 步骤

1. 启动MySQL监视器：

   ```shell
   mysql -u root -p
   ```

2. 为Druid和Superset元数据创建数据库：

   ```sql
   CREATE DATABASE druid DEFAULT CHARACTER SET utf8;
   CREATE DATABASE superset DEFAULT CHARACTER SET utf8;
   ```

3. 创建`druid`和`superset`用户账户，用您的密码替换`IDENTIFIED BY`最后的字符串：

   ```sql
   CREATE USER 'druid'@'%' IDENTIFIED BY '9oNio)ex1ndL';
   CREATE USER 'superset'@'%' IDENTIFIED BY '9oNio)ex1ndL';
   ```

4. 为`druid`账户分配权限：

   ```sql
   GRANT ALL PRIVILEGES ON *.* TO 'druid'@'%' WITH GRANT OPTION;
   GRANT ALL PRIVILEGES ON *.* TO 'superset'@'%' WITH GRANT OPTION;
   ```

5. 提交操作：

   ```sql
   commit;
   ```
