# 验证主机

**Confirm Hosts**提示您去验证Ambari是否已经定位了您的集群中的主机，并检查这些主机以确认它们拥有继续安装所需的目录，包，和进程。

如果有任何选定的主机出错，您可以选择对应的复选框并通过灰色的**Remove Selected**按钮将其移除。要移除单个主机，点击Action列的白色小**Remove**按钮。

在屏幕的底部，您可以注意到一个黄色的框，它报告的的是一些在检查过程中发现的警告信息。比如，您的主机可能已经有了一个`wget`或者`curl`的副本。选择**Click here to see the warnings**去查看被检测到并造成了这些警告的列表。警告页页提供了对python脚本的访问，这能帮助您清除任何您可能遇到的问题，并让您运行

```shell
Return Checks
```

。

> **[info] 注意**
>
> 在集群安装向导中，如果在"Confirm Hosts"这一步Ambari Agent无法注册到Ambari Server。点击**Failed**链接到向导页以展示Amgent的日志。下面的日志条目展示了注册过程中Agent与Server之间的SSl连接失败信息：
>
> `INFO 2014-04-02 04:25:22,669 NetUtil.py:55 - Failed to connect to https://<ambari-server>:8440/cert/ca due to [Errno 1] _ssl.c:492: error:100AE081:elliptic curve routines:EC_GROUP_new_by_curve_name:unknown group`

当您对主机列表感到满意时，选择**Next**。

## 接下来的步骤

[选择服务](../08-choose-services/README.md)