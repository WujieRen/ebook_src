# 配置Ambari使用RedHat Satellite或Spacewalk

Ambari Server	使用版本定义文件（VDF）理解版本中包含了那些产品和组件的版本。为了让Ambari能够更好地与Satellite或Spacewalk一起工作，您必须在安装或升级集群时为您集群中特定版本的操作系统创建自定义VDF文件，以告知Ambari所使用的RedHat Satellite或Spacewalk通道的名字。

要创建自定义VDF文件，我们建议您将一个我们HDP 3.0 Repostories【此处加超链接】中现有的VDF下载至您本地桌面。下载完成后，用您喜欢的编辑器打开该文件，为每个仓库更改<repoid/&gt;标签的内容以匹配先前配置的Satellite或Spacewalk通道名。比如下面这个例子，我已经在Satellite或Spacewalk中创建了以下通道：

**表6.1 Hortonwoks仓库通道名举例**

| **Hortonwoks仓库** | **RedHat Satellite或Spacewalk通道名** |
| ------------------ | ------------------------------------- |
| HDP-3.0.0.0        | hdp_3.0.0.0                           |
| HDP-3.0-GPL*       | hdp_3.0_gpl                           |
| HDP-UTILS-1.1.0.22 | hdp_utils_1.1.0.22                    |

\*  如果在您的集群中将会使用LZO压缩，查看配置LZO压缩【此处加超链接】以获取更多信息。

```xml
<repository-info>
    <os family="redhat7">
      <package-version>3_0_0_0_*</package-version>
      <repo>
 <baseurl>http://public-repo-1.hortonworks.com/HDP/centos7/3.x/updates/3.0.0.0</baseurl>
        <repoid>hdp_3.0.0.0</repoid>
        <reponame>HDP</reponame>
        <unique>true</unique>
      </repo>
      <repo>
 <baseurl>http://public-repo-1.hortonworks.com/HDP-GPL/centos7/3.x/updates/3.0.0.0</baseurl>
        <repoid>hdp_3.0_gpl</repoid>
        <reponame>HDP-GPL</reponame>
        <unique>true</unique>
        <tags>
          <tag>GPL</tag>
        </tags>
      </repo>
      <repo>
 <baseurl>http://public-repo-1.hortonworks.com/HDP-UTILS-1.1.0.22/repos/centos7</baseurl>
        <repoid>hdp_utils_1.1.0.22</repoid>
        <reponame>HDP-UTILS</reponame>
        <unique>false</unique>
      </repo>
    </os>
  </repository-info>
```

## 接下来的步骤

[将自定义VDF导入Ambari](./import-vdf.md)