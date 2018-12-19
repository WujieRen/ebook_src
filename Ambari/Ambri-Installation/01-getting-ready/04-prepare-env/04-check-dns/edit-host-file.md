# 编辑Host文件

1. 使用文本编辑器打开您集群中的每台主机上的hosts文件。比如：

   ```shell
   vi /etc/hosts
   ```

2. 对应于集群中的主机，有几台主机就添加几行。每行的内容是主机的IP地址和该主机的全限定域名。比如：

   ```shell
   1.2.3.4 <fully.qualified.domain.name>
   ```

> **[warning] 警告**
>
> 不要移除hosts文件中类似于下面两行的内容。移除或编辑该内容会导致需要网络功能的程序无法执行。
>
> ```
> 127.0.0.1 localhost.localdomain localhost
> ::1 localhost6.localdomain6 localhost6
> ```

