# 选择服务

根据在**Select Stack**设置中选择的Stack版本，将向您展示能够安装在您集群上的可选服务。Stack由包含很多服务。您可以选在现在就安装可用的服务，也可以安装完Ambari后添加。默认情况下集群安装向导会勾选所有可以安装的服务。

SmartSense是强制部署的。您不能您不能在安装向导中取消安装SmartSense的选项。

![](..\..\image\smartsense.png)

去选择您想要部署的服务吧。

## 步骤

1. 勾选**none**清除所有已选，或者选择**all**选择列表中的所有服务。

2. 勾选或取消单个复选框定义一系列现在要安装的服务。

3. 在选好现在要安装的服务后，点击**Next**。

   > **[info] 注意**
   >
   > 在添加服务后，您可能需要执行额外的任务，更多关于安装和配置特定服务的信息见下列主题：
   >
   > - [安装Apache Spark](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/installing-spark/content/installing_spark.html)
   > - [安装和配置Apache Storm](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/installing-configuring-storm/content/installing_apache_storm.html)
   > - [为Kerberos配置Storm](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/authentication-with-kerberos/content/kerberos_storm_configuring_storm_for_kerberos_using_ambari.html)
   > - [安装并配置Apache Kafka](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/installing-configuring-kafka/content/installing_kafka.html)
   > - [为Kerberos配置Kafka](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/authentication-with-kerberos/content/kerberos_kafka_configuring_kafka_for_kerberos_using_ambari.html)
   > - [安装Apache Atlas](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/installing-atlas/content/migrating_atlas_metadata_when_upgrading_to_hdp-3_0.html)
   > - [用Ambari安装Apache Ranger](https://docs.hortonworks.com/HDPDocuments/HDP3/HDP-3.1.0/installing-ranger/content/installing_ranger_using_ambari.html)
   > - [安装Apache Solr搜索引擎](https://docs.hortonworks.com/HDPDocuments/HDPS/HDPS-4.0.0/bk_solr-search-installation/content/ch_hdp-search.html)

## 接下来的步骤

[分配Masters](../09-assign-masters/README.md)

## More Information

[添加服务](https://docs.hortonworks.com/HDPDocuments/Ambari-2.7.3.0/managing-and-monitoring-ambari/content/amb_add_a_service.html)

[SmartSense介绍](https://docs.hortonworks.com/HDPDocuments/SS1/SmartSense-1.5.1/introduction/content/ss_smartsense_intro.html)