# 在集群和主机浏览器上启用NTP

您集群上的所有节点和着您要访问Ambari Web用户界面的机器的时钟必须能够互相同步。

为了安装NTP服务并确保它能够在开启时启动，请在每台主机上运行以下命令：

**RHEL/CentOS/Oracle 7**

```shell
yum install -y ntp
systemctl enable ntpd
```

**SLES**

```shell
zypper install ntp
chkconfig ntp on
```

**Ubuntu**

```shell
apt-get install ntp
update-rc.d ntp defaults
```

**Debian**

```shell
apt-get install ntp
update-rc.d ntp defaults
```

