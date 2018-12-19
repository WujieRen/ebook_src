# 指定要与SAM和Schema Registry一起使用的Oracle数据库

## 关于该任务

您可能想为SAM和Schema Registry使用Oracle数据库。我们支持Oracle数据库的12c和11g两个版本。

## 先决条件

您已经安装且配置了一个Oracle数据库。

## 步骤

1. 注册Oracle JDBC驱动jar。

   ```shell
   sudo ambari-server setup --jdbc-db=oracle --jdbc-driver=/usr/share/java/ojdbc.jar
   ```

2. 在SAM的一个Schema Registry配置页面，选择Oracle为数据库类型并提供必要的Oracle服务JDBC验证和连接信息。