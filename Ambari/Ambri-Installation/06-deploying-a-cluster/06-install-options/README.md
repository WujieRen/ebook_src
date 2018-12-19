# 安装选项

为了建立集群，集群安装向导会提示您有关如何配置的一般信息。您需要提供您所有主机的全限定名。安装向导也需要访问您设置免密SSH时生成的私匙文件。使用主机名和密匙文件，安装向导可以定位，访问，以及与集群中的所有主机进行安全地交互。

## 步骤

1. 在**Target Hosts**中，输入您的主机名列表，每行一个。

   您可以在方括号中使用范围以指定大量主机。比如，对于从host01.domain到host10.domain的所有主机可以用`host[01-10].domain`。

   > **[info] 注意**
   >
   > 如果您部署在EC2上，请使用`internal Private DNS`（内部私有DNS）主机名。

2. 如果您想要Ambari通过SSH在您所有的主机上自动安装Ambari Agent，请选择**Provide your SSH Private Key**，或者使用**Host Registration Informatin**部分的**Choose File**按钮以查找与您先前在所有主机上安装公匙相匹配的私匙，或者您可以手动将该密匙剪贴到文本框中。

3. 输入与您选定的SSh密匙相匹配的用户名。如果您不想使用`root`，您必须提供一个不用输入密码就可以执行`sudo`的用户账户的用户名。如果在您的环境中的主机上配置的的SSH端口不是22，您也可以更改为您配置的端口号。

4. 如果您不想Ambari自动安装Ambari Agent，选择**Perform manual registration**。

5. 选择**Register and Confirm**以继续。

## 接下来的步骤

[验证主机](../07-confirm-hosts/README.md)

## More Information

[设置免密SSH](../../01-getting-ready/04-prepare-env/01-set-up-ssh/README.md)

[手动安装Ambari Agents](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_installing_ambari_agents_manually.html)