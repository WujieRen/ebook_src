# 设置免密SSH

## 关于该任务

为了使Ambari Server能够在您集群的所有主机上自动地安装Ambari Agent，您必须在Ambari Server主机和集群中所有别的主机之间设置免密SSH连接。Ambari Server主机使用SSH公匙验证并远程访问和安装Ambari Agent。

> **[info] 注意**
>
> 您可以选择在每个集群主机上手动安装Ambari Agent。在这种情况下，您不需要生成以及分发SSH公匙。

## 步骤

1. 在Ambari Server主机上生成公匙和私匙。

   ```shell
   ssh-keygen
   ```

2. 将SSH公匙（id_rsa.pub）复制到目标主机上的根账户。

   ```shell
   .ssh/id_rsa
   ```

   ```shell
   .ssh/id_rsa.pub
   ```

3. 将SSH公匙添加到目标主机上的authorized_keys文件中。

   ```shell
   cat id_rsa.pub >> authorized_keys
   ```

4. 您可能需要设置目标主机上的.ssh文件夹（设为700）和authorized_keys文件所在目录（设为600）的权限——这取决于您的SSH版本。

   ```
   chmod 700 ~/.ssh
   ```

   ```shell
   chmod 600 ~/.ssh/authorized_keys
   ```

5. 在Ambari Server主机上测试连接，确保您可以使用SSH连接每一台主机而不用输入密码。

   ```
   ssh root@<remote.target.host>
   ```

   `<remote.target.host>` 的值涵盖了您集群中的每一台主机的主机名。

6. 如果在您第一次连接时出现以下警告信息：`Are you sure you want to continue connecting (yes/no)?` 输入 `Yes`.

7. 在您将要运行基于web的Ambari安装向导的主机上，保存一份SSH私匙的副本。

> **[info] 注意**
>
> 如果非root账户不需要输入密码就可以执行 `sudo` ，那么也可以使用该账户。

## More Information

[手动安装Ambari Agent](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_installing_ambari_agents_manually.html)

