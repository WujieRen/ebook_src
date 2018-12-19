# 在MySQL中配置SAM和Schema并注册元数据

## 步骤

1. 启动MySQL监视器：

   ```shell
   mysql -u root -p
   ```

2. 为Schema Registry和SAM元数据创建数据库：

   ```sql
   create database registry;
   create database streamline;
   ```

3. 为Schema Registry和SAM用户创建用户账户，用您的密码替换掉最后的`IDENTIFIED BY`字符串：

   ```shell
   CREATE USER 'registry'@'%' IDENTIFIED BY 'R12$%34qw';
   CREATE USER 'streamline'@'%' IDENTIFIED BY 'R12$%34qw';
   ```

4. 给您的用户账户分配权限：

   ```sql
   GRANT ALL PRIVILEGES ON registry.* TO 'registry'@'%' WITH GRANT OPTION ;
   GRANT ALL PRIVILEGES ON streamline.* TO 'streamline'@'%' WITH GRANT OPTION ;
   ```

5. 提交操作：

   ```sql
   commit;
   ```