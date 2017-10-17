#Steps taken during Activation of HA for HDFS

For the journal logs, i created directory /dfs/jn , where owner is hdfs:hadoop,
since 2 of ZooKeeper nodes are also DataNodes, just to avoid having service writing to disks that are dedicated to HDFS service.

Followed up tutorial, CDH 5.8.x specific on how to enable HA.

[https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cdh_hag_hdfs_ha_cdh_components_config.html#topic_2_6](url)

Also configured Hive and HUE services to take advantage of HDFS HA.

![Image of 3_HDFS_HA.png](https://github.com/Mladen-Trampic-SRB-1989/SEBC/blob/master/storage/labs/3_HDFS_HA.png)