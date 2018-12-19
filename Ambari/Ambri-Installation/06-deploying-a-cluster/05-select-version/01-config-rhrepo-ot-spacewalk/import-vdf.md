# 将自定义的VDF导入Ambari

要将自定义的VDF导入Ambari，请按以下步骤操作：

1. 在集群安装向导中的**Select Version**这一步，点击HDP版本下拉列表并选择**Add Version**。

   ![](..\..\..\image\select_version.png)

2. 在**Add Version**中，选择**Upload Version Definition File**并点击**Choose File**。选择您本地保存VDF的目录，点击**Choose FIle**，然后点击**Read Version Info**。

   ![](..\..\..\image\add_version.png)

3. 在**Select Version**中，点击**Use Local Repository**单选按钮以告知Ambari仓库不要从网络下载仓库。

4. 点击**Use RedHat Satellite/Spacewalk**复选框。

5. 验证您的操作系统版本仓库名是否正确，并在您的RedHat Satellite或Spacewalk安装中匹配正确的VDF和通道名。

   ![](..\..\..\image\custom_vdf.png)

6. 点击**Next**。

## 接下来的步骤

[安装选项](../../06-install-options/README.md)

## More Information

[为Ambari设置网络代理服务](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_setting_up_ambari_to_use_an_internet_proxy_server.html)

[使用本地仓库](../../../02-using-a-local-repository/README.md)