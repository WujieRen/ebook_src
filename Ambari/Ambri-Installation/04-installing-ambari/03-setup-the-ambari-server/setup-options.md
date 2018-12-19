# 选项设置

在Ambari Server配置过程中，下列参数经常会用到。

**-j（或者 --java-home）**
指定JAVA_HOME路径以供Ambari Server和集群中的所有主机使用。默认情况下，如果您不指定该该选项，Ambari Server设置程序会将Oracle JDK 1.8和附带的Java加密扩展策略文件下载至`/var/lib/ambari-server/resources`。随后，Ambari Server会将JDK安装到`/usr/jdk64`。

如果您打算使用其他的可选JDK而不是默认的Oracle JDK 1.8，请使用该选项，您必须在Ambari Server设置程序执行时在所有的主机上手动下载安装JDK并配置JAVA HOME路径（其实就是配置环境变量）。如果您打算使用Kerberos，您也必须在所有主机上安装Java加密扩展。

该路径必须在所有主机上可用。比如：

```shell
ambari-server setup –j /usr/java/default
```

**--jdbc-driver**
指的是JDBC驱动JAR文件的路径。用该选项指定JDBC驱动JAR文件的路径，而且要确保在配置时该路径对于Ambari Server可用以便Ambari Server将其分发到其他节点。使用该选项的同时需要要用`--jdbc-db`选项指定数据库类型。

**--jdbc-db**
指定数据库类型。可选值：[postgres | mysql | oracle]。使用该选项的同时需要使用`--jdbc-driver`选项指定JDBC驱动JAR文件的位置。

**--s（或者--SILENT）**
静默运行设置程序。即接受所有的默认设置。比如：

- 默认“root”为ambari-server的用户账户。

- Oracle 1.8 JDK（安装在/usr/jdk64）。该值可以被覆盖——通过-j选项指定一个现有的JDK路径。

- 用内嵌的PostgreSQL作为Ambari的默认数据库（数据库名为ambari）。

  > **[warning] 警告**
  >
  > 如果选择静默安装选项， 意味着Oracle JDK将被安装而且您同意Oracle二进制代码许可协议。
  >
  > 如果您不同意该许可条款，请勿使用该选项。（即勿使用默认安装）
  >
  > 如果Ambari服务器被防火墙保护，那么在下载JDK时，您必须用命令指定ambari-server配置程序使用使用代理。比如：
  >
  > ```shell
  > export http_proxy=http://{username}:{password}@{proxyHost}:{proxyPort}
  > ambari-server setup
  > ```
  >
  > {username}和{password}是可选的。
  >
  > 如果在有防火墙的环境中您没有定义可用的http_proxy环境变量，Oracle JDK下载会失败。

如果您想用非root用户运行Ambari Server，您必须以交互模式运行配置程序。当弹出自定义ambari-server用户账户的提示时，提供相应的账户信息。

**--enable-lzo-under-gpl-license**
使用该选项去下载并安装LZO压缩，符合通用公共许可证规范。

**-v（--verbose）**
在配置时将详细信息和警告信息输出至控制台。

**-g（或者--debug）**
在配置时将调试信息输出至控制台。

## More Information

[JDK需求](https://supportmatrix.hortonworks.com/)

[配置Ambari使用非root用户](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/securing-credentials/content/ambari_sec_configuring_ambari_for_non_root.html)

[配置LZO压缩](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_configuring_lzo_compression.html)

[Oracle Java许可证条款](https://www.oracle.com/technetwork/java/javase/terms/license/index.html)





