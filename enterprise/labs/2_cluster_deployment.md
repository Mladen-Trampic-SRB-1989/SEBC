* Browse or use curl on the endpoint ./api/v2/cm/deployment
  * Command used :
  ```
   curl -X GET -u "```:bowtie:```:```:bowtie:```" -i http://ec2-54-93-198-167.eu-central-1.compute.amazonaws.com:7180/api/v2/cm/deployment
  ```
  * Output :
  ```
  HTTP/1.1 200 OK
  Expires: Thu, 01-Jan-1970 00:00:00 GMT
  Set-Cookie: CLOUDERA_MANAGER_SESSIONID=1549uq6ur1jjh1j5bpr1r3gpfz;Path=/;HttpOnly
  Content-Type: application/json
  Date: Wed, 18 Oct 2017 09:16:31 GMT
  Transfer-Encoding: chunked
  Server: Jetty(6.1.26.cloudera.4)
  
  {
    "timestamp" : "2017-10-18T09:16:31.034Z",
    "clusters" : [ {
      "name" : "Mladen-Trampic-SRB-1989",
      "version" : "CDH5",
      "services" : [ {
        "name" : "hive",
        "type" : "HIVE",
        "config" : {
          "roleTypeConfigs" : [ {
            "roleType" : "HIVEMETASTORE",
            "items" : [ {
              "name" : "hive_metastore_java_heapsize",
              "value" : "593494016"
            } ]
          }, {
            "roleType" : "HIVESERVER2",
            "items" : [ {
              "name" : "hiveserver2_java_heapsize",
              "value" : "593494016"
            }, {
              "name" : "hiveserver2_spark_driver_memory",
              "value" : "966367641"
            }, {
              "name" : "hiveserver2_spark_executor_cores",
              "value" : "4"
            }, {
              "name" : "hiveserver2_spark_executor_memory",
              "value" : "3433247539"
            }, {
              "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
              "value" : "102"
            }, {
              "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
              "value" : "577"
            } ]
          } ],
          "items" : [ {
            "name" : "hive_metastore_database_host",
            "value" : "ip-172-31-33-245"
          }, {
            "name" : "hive_metastore_database_password",
            "value" : "hive_pwd"
          }, {
            "name" : "mapreduce_yarn_service",
            "value" : "yarn"
          }, {
            "name" : "zookeeper_service",
            "value" : "zookeeper"
          } ]
        },
        "roles" : [ {
          "name" : "hive-GATEWAY-46d66da78f31d600e4fc6534cd0de64e",
          "type" : "GATEWAY",
          "hostRef" : {
            "hostId" : "db8eca76-eb13-4241-af38-5a998c5f8f60"
          },
          "config" : {
            "items" : [ ]
          }
        }, {
          "name" : "hive-GATEWAY-7ebce781f4d661a530d5ce5fade65bf5",
          "type" : "GATEWAY",
          "hostRef" : {
            "hostId" : "0bacc6f3-f209-4b1b-9678-2e26be0e75c5"
          },
          "config" : {
            "items" : [ ]
          }
        }, {
          "name" : "hive-GATEWAY-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "GATEWAY",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ ]
          }
        }, {
          "name" : "hive-GATEWAY-db66b8a09a1989cd770b0998e20fc8b1",
          "type" : "GATEWAY",
          "hostRef" : {
            "hostId" : "143ab6ba-f0e0-4ae3-a356-33762e1cd3f9"
          },
          "config" : {
            "items" : [ ]
          }
        }, {
          "name" : "hive-GATEWAY-dd31d30192d3706e026bffa71d3ae922",
          "type" : "GATEWAY",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ ]
          }
        }, {
          "name" : "hive-HIVEMETASTORE-dd31d30192d3706e026bffa71d3ae922",
          "type" : "HIVEMETASTORE",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "5mwahavmwrqpuoxitpdad9ppo"
            } ]
          }
        }, {
          "name" : "hive-HIVESERVER2-dd31d30192d3706e026bffa71d3ae922",
          "type" : "HIVESERVER2",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "21g54yon444byjw2621hnc693"
            } ]
          }
        } ],
        "displayName" : "Hive"
      }, {
        "name" : "zookeeper",
        "type" : "ZOOKEEPER",
        "config" : {
          "roleTypeConfigs" : [ {
            "roleType" : "SERVER",
            "items" : [ {
              "name" : "zookeeper_server_java_heapsize",
              "value" : "593494016"
            } ]
          } ],
          "items" : [ ]
        },
        "roles" : [ {
          "name" : "zookeeper-SERVER-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "SERVER",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "es51uo99jcnh9yuve4s8y7cl9"
            }, {
              "name" : "serverId",
              "value" : "2"
            } ]
          }
        }, {
          "name" : "zookeeper-SERVER-db66b8a09a1989cd770b0998e20fc8b1",
          "type" : "SERVER",
          "hostRef" : {
            "hostId" : "143ab6ba-f0e0-4ae3-a356-33762e1cd3f9"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "eebc87ysa496ulucfne1pshm0"
            }, {
              "name" : "serverId",
              "value" : "1"
            } ]
          }
        }, {
          "name" : "zookeeper-SERVER-dd31d30192d3706e026bffa71d3ae922",
          "type" : "SERVER",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "7ho06r6cuwksg9n8szm4gy6vq"
            }, {
              "name" : "serverId",
              "value" : "3"
            } ]
          }
        } ],
        "displayName" : "ZooKeeper"
      }, {
        "name" : "hue",
        "type" : "HUE",
        "config" : {
          "roleTypeConfigs" : [ ],
          "items" : [ {
            "name" : "database_password",
            "value" : "hue_pwd"
          }, {
            "name" : "database_type",
            "value" : "mysql"
          }, {
            "name" : "hive_service",
            "value" : "hive"
          }, {
            "name" : "hue_webhdfs",
            "value" : "hdfs-HTTPFS-dd31d30192d3706e026bffa71d3ae922"
          }, {
            "name" : "oozie_service",
            "value" : "oozie"
          }, {
            "name" : "zookeeper_service",
            "value" : "zookeeper"
          } ]
        },
        "roles" : [ {
          "name" : "hue-HUE_SERVER-dd31d30192d3706e026bffa71d3ae922",
          "type" : "HUE_SERVER",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "3qrie1k94uhnc8x6y83fhm1iq"
            }, {
              "name" : "secret_key",
              "value" : "KcgWf2gKpdZjw4DpmLHm1LDX9pTo1C"
            } ]
          }
        } ],
        "displayName" : "Hue"
      }, {
        "name" : "oozie",
        "type" : "OOZIE",
        "config" : {
          "roleTypeConfigs" : [ {
            "roleType" : "OOZIE_SERVER",
            "items" : [ {
              "name" : "oozie_database_host",
              "value" : "ip-172-31-33-245"
            }, {
              "name" : "oozie_database_password",
              "value" : "oozie_pwd"
            }, {
              "name" : "oozie_database_type",
              "value" : "mysql"
            }, {
              "name" : "oozie_database_user",
              "value" : "oozie"
            }, {
              "name" : "oozie_java_heapsize",
              "value" : "593494016"
            } ]
          } ],
          "items" : [ {
            "name" : "hive_service",
            "value" : "hive"
          }, {
            "name" : "mapreduce_yarn_service",
            "value" : "yarn"
          }, {
            "name" : "zookeeper_service",
            "value" : "zookeeper"
          } ]
        },
        "roles" : [ {
          "name" : "oozie-OOZIE_SERVER-dd31d30192d3706e026bffa71d3ae922",
          "type" : "OOZIE_SERVER",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "3s17qngnj5hx31qgzs4ayaprj"
            } ]
          }
        } ],
        "displayName" : "Oozie"
      }, {
        "name" : "yarn",
        "type" : "YARN",
        "config" : {
          "roleTypeConfigs" : [ {
            "roleType" : "GATEWAY",
            "items" : [ {
              "name" : "mapred_reduce_tasks",
              "value" : "8"
            }, {
              "name" : "mapred_submit_replication",
              "value" : "2"
            } ]
          }, {
            "roleType" : "JOBHISTORY",
            "items" : [ {
              "name" : "mr2_jobhistory_java_heapsize",
              "value" : "593494016"
            } ]
          }, {
            "roleType" : "NODEMANAGER",
            "items" : [ {
              "name" : "yarn_nodemanager_heartbeat_interval_ms",
              "value" : "100"
            }, {
              "name" : "yarn_nodemanager_local_dirs",
              "value" : "/1/yarn/nm,/2/yarn/nm"
            }, {
              "name" : "yarn_nodemanager_log_dirs",
              "value" : "/1/yarn/container-logs,/2/yarn/container-logs"
            }, {
              "name" : "yarn_nodemanager_resource_cpu_vcores",
              "value" : "4"
            }, {
              "name" : "yarn_nodemanager_resource_memory_mb",
              "value" : "4939"
            } ]
          }, {
            "roleType" : "RESOURCEMANAGER",
            "items" : [ {
              "name" : "resource_manager_java_heapsize",
              "value" : "593494016"
            }, {
              "name" : "yarn_scheduler_maximum_allocation_mb",
              "value" : "4939"
            }, {
              "name" : "yarn_scheduler_maximum_allocation_vcores",
              "value" : "3"
            } ]
          } ],
          "items" : [ {
            "name" : "hdfs_service",
            "value" : "hdfs"
          }, {
            "name" : "rm_dirty",
            "value" : "false"
          }, {
            "name" : "rm_last_allocation_percentage",
            "value" : "90"
          }, {
            "name" : "yarn_service_cgroups",
            "value" : "false"
          }, {
            "name" : "yarn_service_lce_always",
            "value" : "false"
          }, {
            "name" : "zk_authorization_secret_key",
            "value" : "aO8QbHXfUMwjfYlUqFflSG1mchVslt"
          }, {
            "name" : "zookeeper_service",
            "value" : "zookeeper"
          } ]
        },
        "roles" : [ {
          "name" : "yarn-JOBHISTORY-dd31d30192d3706e026bffa71d3ae922",
          "type" : "JOBHISTORY",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "99s3v5qxllblfawpv1zhdhx0w"
            } ]
          }
        }, {
          "name" : "yarn-NODEMANAGER-46d66da78f31d600e4fc6534cd0de64e",
          "type" : "NODEMANAGER",
          "hostRef" : {
            "hostId" : "db8eca76-eb13-4241-af38-5a998c5f8f60"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "d7reultaslyog68w29ybr875r"
            } ]
          }
        }, {
          "name" : "yarn-NODEMANAGER-7ebce781f4d661a530d5ce5fade65bf5",
          "type" : "NODEMANAGER",
          "hostRef" : {
            "hostId" : "0bacc6f3-f209-4b1b-9678-2e26be0e75c5"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "b36bmlmvpf9k9waz8iqsrnq5y"
            } ]
          }
        }, {
          "name" : "yarn-NODEMANAGER-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "NODEMANAGER",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "i94euqr8jm253kmj64oa94f4"
            } ]
          }
        }, {
          "name" : "yarn-NODEMANAGER-db66b8a09a1989cd770b0998e20fc8b1",
          "type" : "NODEMANAGER",
          "hostRef" : {
            "hostId" : "143ab6ba-f0e0-4ae3-a356-33762e1cd3f9"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "1295t0ony6o4eclu3y44nmi75"
            } ]
          }
        }, {
          "name" : "yarn-RESOURCEMANAGER-dd31d30192d3706e026bffa71d3ae922",
          "type" : "RESOURCEMANAGER",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "rm_id",
              "value" : "83"
            }, {
              "name" : "role_jceks_password",
              "value" : "4b8my1ambf0qu7362lsz1byy7"
            } ]
          }
        } ],
        "displayName" : "YARN (MR2 Included)"
      }, {
        "name" : "hdfs",
        "type" : "HDFS",
        "config" : {
          "roleTypeConfigs" : [ {
            "roleType" : "BALANCER",
            "items" : [ {
              "name" : "balancer_java_heapsize",
              "value" : "593494016"
            } ]
          }, {
            "roleType" : "DATANODE",
            "items" : [ {
              "name" : "dfs_data_dir_list",
              "value" : "/1/dfs/dn,/2/dfs/dn"
            }, {
              "name" : "dfs_datanode_du_reserved",
              "value" : "3948976537"
            }, {
              "name" : "dfs_datanode_failed_volumes_tolerated",
              "value" : "1"
            }, {
              "name" : "dfs_datanode_max_locked_memory",
              "value" : "4294967296"
            } ]
          }, {
            "roleType" : "GATEWAY",
            "items" : [ {
              "name" : "dfs_client_use_trash",
              "value" : "true"
            } ]
          }, {
            "roleType" : "JOURNALNODE",
            "items" : [ {
              "name" : "dfs_journalnode_edits_dir",
              "value" : "/dfs/jn"
            } ]
          }, {
            "roleType" : "NAMENODE",
            "items" : [ {
              "name" : "dfs_name_dir_list",
              "value" : "/1/dfs/nn,/2/dfs/nn"
            }, {
              "name" : "dfs_namenode_servicerpc_address",
              "value" : "8022"
            }, {
              "name" : "namenode_java_heapsize",
              "value" : "593494016"
            } ]
          }, {
            "roleType" : "SECONDARYNAMENODE",
            "items" : [ {
              "name" : "fs_checkpoint_dir_list",
              "value" : "/1/dfs/snn"
            }, {
              "name" : "secondary_namenode_java_heapsize",
              "value" : "593494016"
            } ]
          } ],
          "items" : [ {
            "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
            "value" : "snJ2vmzAIecVkO0SRxXiSlK7wF7uPe"
          }, {
            "name" : "dfs_ha_fencing_methods",
            "value" : "shell(true)"
          }, {
            "name" : "fc_authorization_secret_key",
            "value" : "A3XUxkgyqwV3FKuJD9m7LVhCqiyjvM"
          }, {
            "name" : "http_auth_signature_secret",
            "value" : "vPUqcR0g4BZEqljghUCXiv0o2Uqloo"
          }, {
            "name" : "rm_dirty",
            "value" : "false"
          }, {
            "name" : "rm_last_allocation_percentage",
            "value" : "10"
          }, {
            "name" : "zookeeper_service",
            "value" : "zookeeper"
          } ]
        },
        "roles" : [ {
          "name" : "hdfs-BALANCER-dd31d30192d3706e026bffa71d3ae922",
          "type" : "BALANCER",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ ]
          }
        }, {
          "name" : "hdfs-DATANODE-46d66da78f31d600e4fc6534cd0de64e",
          "type" : "DATANODE",
          "hostRef" : {
            "hostId" : "db8eca76-eb13-4241-af38-5a998c5f8f60"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "5n5wto0qbi4q0fmu4unptv0g"
            } ]
          }
        }, {
          "name" : "hdfs-DATANODE-7ebce781f4d661a530d5ce5fade65bf5",
          "type" : "DATANODE",
          "hostRef" : {
            "hostId" : "0bacc6f3-f209-4b1b-9678-2e26be0e75c5"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "6h2m0afmr9ec4kf46sr7lld9g"
            } ]
          }
        }, {
          "name" : "hdfs-DATANODE-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "DATANODE",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "7crfph3nztk2xrumjcv0j6eb6"
            } ]
          }
        }, {
          "name" : "hdfs-DATANODE-db66b8a09a1989cd770b0998e20fc8b1",
          "type" : "DATANODE",
          "hostRef" : {
            "hostId" : "143ab6ba-f0e0-4ae3-a356-33762e1cd3f9"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "6g3kl4cmcl296bahwvejeeq7p"
            } ]
          }
        }, {
          "name" : "hdfs-FAILOVERCONTROLLER-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "FAILOVERCONTROLLER",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "l9f11paxiks1jw4hjf5b3k5g"
            } ]
          }
        }, {
          "name" : "hdfs-FAILOVERCONTROLLER-dd31d30192d3706e026bffa71d3ae922",
          "type" : "FAILOVERCONTROLLER",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "chhryxlxey3be93dqs2wz2qth"
            } ]
          }
        }, {
          "name" : "hdfs-HTTPFS-dd31d30192d3706e026bffa71d3ae922",
          "type" : "HTTPFS",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "bqyf3uzv51ffsnzwyd27mr7ed"
            } ]
          }
        }, {
          "name" : "hdfs-JOURNALNODE-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "JOURNALNODE",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "1xlxu3fehi11enx8npgkotzt8"
            } ]
          }
        }, {
          "name" : "hdfs-JOURNALNODE-db66b8a09a1989cd770b0998e20fc8b1",
          "type" : "JOURNALNODE",
          "hostRef" : {
            "hostId" : "143ab6ba-f0e0-4ae3-a356-33762e1cd3f9"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "7gkvpvx1y3dgtqon2nsewa0gk"
            } ]
          }
        }, {
          "name" : "hdfs-JOURNALNODE-dd31d30192d3706e026bffa71d3ae922",
          "type" : "JOURNALNODE",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "role_jceks_password",
              "value" : "f46pbbb6zcr1ciatgfq7iwgqc"
            } ]
          }
        }, {
          "name" : "hdfs-NAMENODE-9902c6dcc39d5a552569c9b029ba5e18",
          "type" : "NAMENODE",
          "hostRef" : {
            "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c"
          },
          "config" : {
            "items" : [ {
              "name" : "autofailover_enabled",
              "value" : "true"
            }, {
              "name" : "dfs_federation_namenode_nameservice",
              "value" : "Mladen-Trampic-SRB-1989"
            }, {
              "name" : "dfs_namenode_quorum_journal_name",
              "value" : "Mladen-Trampic-SRB-1989"
            }, {
              "name" : "namenode_id",
              "value" : "92"
            }, {
              "name" : "role_jceks_password",
              "value" : "3slykqb4i9bnfnov0gpypdk12"
            } ]
          }
        }, {
          "name" : "hdfs-NAMENODE-dd31d30192d3706e026bffa71d3ae922",
          "type" : "NAMENODE",
          "hostRef" : {
            "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
          },
          "config" : {
            "items" : [ {
              "name" : "autofailover_enabled",
              "value" : "true"
            }, {
              "name" : "dfs_federation_namenode_nameservice",
              "value" : "Mladen-Trampic-SRB-1989"
            }, {
              "name" : "dfs_namenode_quorum_journal_name",
              "value" : "Mladen-Trampic-SRB-1989"
            }, {
              "name" : "namenode_id",
              "value" : "85"
            }, {
              "name" : "role_jceks_password",
              "value" : "2giitznclcpd5icfnxe07crc3"
            } ]
          }
        } ],
        "displayName" : "HDFS"
      } ]
    } ],
    "hosts" : [ {
      "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6",
      "ipAddress" : "172.31.33.245",
      "hostname" : "ip-172-31-33-245.eu-central-1.compute.internal",
      "rackId" : "/default",
      "config" : {
        "items" : [ ]
      }
    }, {
      "hostId" : "0bacc6f3-f209-4b1b-9678-2e26be0e75c5",
      "ipAddress" : "172.31.41.58",
      "hostname" : "ip-172-31-41-58.eu-central-1.compute.internal",
      "rackId" : "/default",
      "config" : {
        "items" : [ ]
      }
    }, {
      "hostId" : "8076db29-bdaf-4e16-bf07-47dda8f5c07c",
      "ipAddress" : "172.31.42.124",
      "hostname" : "ip-172-31-42-124.eu-central-1.compute.internal",
      "rackId" : "/default",
      "config" : {
        "items" : [ ]
      }
    }, {
      "hostId" : "143ab6ba-f0e0-4ae3-a356-33762e1cd3f9",
      "ipAddress" : "172.31.45.235",
      "hostname" : "ip-172-31-45-235.eu-central-1.compute.internal",
      "rackId" : "/default",
      "config" : {
        "items" : [ ]
      }
    }, {
      "hostId" : "db8eca76-eb13-4241-af38-5a998c5f8f60",
      "ipAddress" : "172.31.45.41",
      "hostname" : "ip-172-31-45-41.eu-central-1.compute.internal",
      "rackId" : "/default",
      "config" : {
        "items" : [ ]
      }
    } ],
    "users" : [ {
      "name" : "Mladen-Trampic-SRB-1989",
      "roles" : [ "ROLE_ADMIN" ],
      "pwHash" : "74bc914d15ea724594ed5cab81cc07c73ee9a18afb19f142e75428ec908ead34",
      "pwSalt" : -7619723085993225849,
      "pwLogin" : true
    }, {
      "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-dd31d30192d3706e026bffa71d3ae922",
      "roles" : [ "ROLE_USER" ],
      "pwHash" : "2d809129453d0124c20014f1ebe30b7e04a48a5c027fb4221da3f0530d80a048",
      "pwSalt" : 7757074524421262821,
      "pwLogin" : true
    }, {
      "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-dd31d30192d3706e026bffa71d3ae922",
      "roles" : [ "ROLE_USER" ],
      "pwHash" : "4a81e1cf4bf1da50098f67e90a74c9c56e0be71469f307ef33e1ea49d5ae126b",
      "pwSalt" : -98170645442128674,
      "pwLogin" : true
    }, {
      "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-dd31d30192d3706e026bffa71d3ae922",
      "roles" : [ "ROLE_USER" ],
      "pwHash" : "b890b8f84a4de363bbdcf2715c2b1fa4f37fa9291e81dadc5450753f604f6986",
      "pwSalt" : -6034366795587625719,
      "pwLogin" : true
    }, {
      "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-dd31d30192d3706e026bffa71d3ae922",
      "roles" : [ "ROLE_USER" ],
      "pwHash" : "e08c6b580b960e9be9ff0ace1b2dd26b0aa3c672c4cb877ec1be687fef740cad",
      "pwSalt" : 4644153623954995456,
      "pwLogin" : true
    }, {
      "name" : "admin",
      "roles" : [ "ROLE_LIMITED" ],
      "pwHash" : "72ad15686f7db63ac40baa2a35449bc30a4f22f23aedc04d7b89cfc03bdd3fce",
      "pwSalt" : -5146046039701454335,
      "pwLogin" : true
    }, {
      "name" : "minotaur",
      "roles" : [ "ROLE_CONFIGURATOR" ],
      "pwHash" : "f5bd9fa11ebfe565d3e39fb57b0f5ddf1fd00bfca244650b90a4279de156fa84",
      "pwSalt" : 4055199226744882007,
      "pwLogin" : true
    } ],
    "versionInfo" : {
      "version" : "5.8.3",
      "buildUser" : "jenkins",
      "buildTimestamp" : "20161019-1013",
      "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
      "snapshot" : false
    },
    "managementService" : {
      "name" : "mgmt",
      "type" : "MGMT",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "EVENTSERVER",
          "items" : [ {
            "name" : "event_server_heapsize",
            "value" : "593494016"
          } ]
        }, {
          "roleType" : "HOSTMONITOR",
          "items" : [ {
            "name" : "firehose_heapsize",
            "value" : "593494016"
          }, {
            "name" : "firehose_non_java_memory_bytes",
            "value" : "805306368"
          } ]
        }, {
          "roleType" : "REPORTSMANAGER",
          "items" : [ {
            "name" : "headlamp_database_host",
            "value" : "ip-172-31-33-245"
          }, {
            "name" : "headlamp_database_name",
            "value" : "rman"
          }, {
            "name" : "headlamp_database_password",
            "value" : "rman_pwd"
          }, {
            "name" : "headlamp_database_user",
            "value" : "rman"
          }, {
            "name" : "headlamp_heapsize",
            "value" : "593494016"
          } ]
        }, {
          "roleType" : "SERVICEMONITOR",
          "items" : [ {
            "name" : "firehose_heapsize",
            "value" : "593494016"
          }, {
            "name" : "firehose_non_java_memory_bytes",
            "value" : "805306368"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "mgmt-ALERTPUBLISHER-dd31d30192d3706e026bffa71d3ae922",
        "type" : "ALERTPUBLISHER",
        "hostRef" : {
          "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5op3h0rt1jf9crd2w1659v4of"
          } ]
        }
      }, {
        "name" : "mgmt-EVENTSERVER-dd31d30192d3706e026bffa71d3ae922",
        "type" : "EVENTSERVER",
        "hostRef" : {
          "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7bjfavwlg8g9vrvbinfs3fh0w"
          } ]
        }
      }, {
        "name" : "mgmt-HOSTMONITOR-dd31d30192d3706e026bffa71d3ae922",
        "type" : "HOSTMONITOR",
        "hostRef" : {
          "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "46dy0276mrovn0duprk1db9tn"
          } ]
        }
      }, {
        "name" : "mgmt-REPORTSMANAGER-dd31d30192d3706e026bffa71d3ae922",
        "type" : "REPORTSMANAGER",
        "hostRef" : {
          "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "espq5298yzxe73w5iwpbtf084"
          } ]
        }
      }, {
        "name" : "mgmt-SERVICEMONITOR-dd31d30192d3706e026bffa71d3ae922",
        "type" : "SERVICEMONITOR",
        "hostRef" : {
          "hostId" : "dbcce002-6d7b-48f0-98ac-2ba5622cc3f6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4hm8lxabymkl6uzvyogjonklx"
          } ]
        }
      } ],
      "displayName" : "Cloudera Management Service"
    },
    "managerSettings" : {
      "items" : [ {
        "name" : "CLUSTER_STATS_START",
        "value" : "10/24/2012 7:00"
      }, {
        "name" : "PUBLIC_CLOUD_STATUS",
        "value" : "ON_PUBLIC_CLOUD"
      }, {
        "name" : "REMOTE_PARCEL_REPO_URLS",
        "value" : "https://archive.cloudera.com/cdh5/parcels/5.8.3,http://ip-172-31-33-245.eu-central-1.compute.internal/cdh5/,http://ip-172-31-33-245.eu-central-1.compute.internal/cdh4/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,http://ip-172-31-33-245.eu-central-1.compute.internal/accumulo/,http://ip-172-31-33-245.eu-central-1.compute.internal/kafka/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
      } ]
    }
  }
  ```