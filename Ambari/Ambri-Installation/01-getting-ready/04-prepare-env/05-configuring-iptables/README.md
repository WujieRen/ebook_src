# 配置iptables

为了让Ambari在设置过程中能够与它部署和管理的主机进行通信，某些特定的端口必须开放且可用。做到这点最简单的方式就是去临时禁用iptables，正如下面所展示的：

- **RHEL/CentOS/Oracle/Amazon Linux**

  ```shell
  systemctl disable firewalld
  service firewalld stop
  ```

- **SLES**

  ```shell
  rcSuSEfirewall2 stop
  chkconfig SuSEfirewall2_setup off
  ```

- **Ubuntu**

  ```shell
  sudo ufw disable
  sudo iptables -X
  sudo iptables -t nat -F
  sudo iptables -t nat -X
  sudo iptables -t mangle -F
  sudo iptables -t mangle -X
  sudo iptables -P INPUT ACCEPT
  sudo iptables -P FORWARD ACCEPT
  sudo iptables -P OUTPUT ACCEPT
  ```

- **Debian**

  ```shell
  sudo iptables -X
  sudo iptables -t nat -F
  sudo iptables -t nat -X
  sudo iptables -t mangle -F
  sudo iptables -t mangle -X
  sudo iptables -P INPUT ACCEPT
  sudo iptables -P FORWARD ACCEPT
  sudo iptables -P OUTPUT ACCEPT
  ```

设置完成后您需要重启iptables服务。如果您的环境中的安全协议阻止禁用iptables服务，您可以在iptables服务开启的情况下继续——如果所有需要的端口开放且可用。

在Ambari Server安装设置过程中Ambari会检查iptables服务是否正在运行。如果iptables服务正在运行，那么将会有一个警告信息出现——提醒您去检查所需端口是否开放并可用的。集群安装向导中的主机验证步骤也会为每个正在运行iptables服务的主机发出警告。

## More Information

[配置网络端口号](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/administering-ambari/content/amb_configuring_network_port_numbers.html)