# MySQL/MariaDB先决条件

在安装Ranger过程中，您必须把变量`log_bin_trust_function_creators`的值修改成`1`。

在RDS Dashboard > Parameter group中（在页面的左侧）：

1. 将MySQL变量`log_bin_trust_function_creators`的值设为`1`。
2. （可选）在Ranger安装完成后，将`log_bin_trust_function_creators`的值重设为初始值。该变量仅仅在安装Ranger的过程中需要设为`1`。

更多信息见：

- Stratalux：当创建RDS实例时，为什么您应该总是使用自定义DB参数组。
- AWS文档 > Amazon RDS DB实例生命周期 >> 用数据库参数组工作
- MySQL 5.7 参考手册 > 存储程序的二进制日志记录