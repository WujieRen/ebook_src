# 选择版本

在这个步骤中，您将为您的集群选择软件版本和交付方式。使用公共仓库要求您有畅通的网络连接。使用本地仓库要求已经配置好了一个包含了所需软件的，在您的网络环境中可以访问的仓库。

## 选择Stack

可用的版本在选项卡中展示。当您选择了一个选项卡时，Ambari将试图找到该Stack可用的版本。清单以一个下拉列表展示。对于选定的版本，将在表中展示其可用的服务以及对应的版本。

![](..\..\image\version.png)

## 选择版本

如果Ambari能够访问网络，那么选定的版本将以选项的形式在下拉列表中展示。如果有某个版本的版本定义文件没有被列出，您可以点击**Add Version...**并上传该版本的VDF文件。另外，如果您无法访问网络或者不确定要安装哪个版本，一个默认版本定义（**Default Version Definition**）也会包含在该下拉列表中。

> **[info] 注意**
>
> 如果您的Ambari Server可以访问网络但是是通过网络代理服务代理的，一定要为Ambari Server设置该代理。

![](..\..\image\proxy.png)

## 选择仓库

Ambari为您提供了从公共仓库（如果您可以访问网络的话）和本地仓库两种选择去下载软件。无论您选择哪种方式，您都可以编辑仓库中的基URL。列表将展示可用的操作系统，而且您也可以在列表中添加/删除操作系统以适应您的环境。

![](..\..\image\repository.png)

该UI展示了基于操作系统家族的基仓库基URL。一定要根据您正在运行的操作系统选择正确的操作系统家族。

  **redhat7**
  Red Hat 7, CentOS 7, Oracle Linux 7, Amazon Linux 2

  **sels12**
  SUSE Linux Enterprise Server 12

  **ubuntu14**
  Ubuntu 14

  **ubuntu16**
  Ubuntu 16

  **ubuntu18**
  Ubuntu 18

  **debian9**
  Debian 9

## 高级选项

有一些可用的高级仓库选项。

- **Skip Repository Base URL validation（Advanced）**：当您选择**Next**时，Ambari会去连接仓库基URL以验证您已经登记了一个有效的仓库。如果没有，将会提示您在继续之前必须修正该错误。
- **Use RedHat Satellite/Spacewalk：**该选项只有在您打算使用本地仓库时可用。当您为软件仓库选择该选项时，您将有责任去配置在Satellite/Spacewallk中的仓库通道；以及去确认对于选定的**stack版本**，该仓库在集群的所有节点上可用。

## More Information

[使用本地的RedHat Satellite或者Spacewalk仓库](./01-config-rhrepo-ot-spacewalk/README.md)