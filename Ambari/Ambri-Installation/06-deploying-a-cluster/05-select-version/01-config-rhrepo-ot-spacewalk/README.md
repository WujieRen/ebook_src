# 使用本地RedHat Satellite或Spacewalk仓库

许多Ambari用户使用RedHat Satellite或者Spacewalk去管理他们集群上的操作系统仓库。配置Ambari使用您的Satellite或Spacewalk基础设施的一般过程是：

1. 确保您已经为您想要使用过的产品版本对应的Hortonworks仓库【此处需要添加超链接】创建了通道。

2. 确保创建的通道在集群的所有机器上可用。

3. 安装并启动Ambari Server。

4. 在开始安装集群之前更新Ambari，以便让它知道不要将仓库管理委托给Satellite或Spacewalk；另外，请在安装或更新包时使用恰当的通道名。

   > **[info] 注意**
   >
   > 请在继续之前为您的通道起好名字。

## 接下来的步骤

[配置Ambari使用RedHat Satellite或Spacewalk](./config-use.md)