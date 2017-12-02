{
  "timestamp" : "2017-11-30T18:07:25.993Z",
  "clusters" : [ {
    "name" : "alexpg06",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "4276092928"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "427609292"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1426509004"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "240"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-10-1-2-181.ec2.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "Hive2017"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-44ce967d70921e570a07ccabfb001fd0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c3978f40160696fadbc02822ef00c65a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-c3978f40160696fadbc02822ef00c65a",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dpq4oqnq2lgd6x1tgyid7bf8o"
          } ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "amlhwibb66ic7421threa0436"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8k95f8nsjfsisiwc7n2owhh4t"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "afhayx2qc4gd63ci8xwb611r5"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7qcvnt7sl8yhj56rjbzbst4cd"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-c3978f40160696fadbc02822ef00c65a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8hlafbj7jfjpw3ddp1fyyxj45"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5hjb5dluav9z7ms1pjxkprfep"
          }, {
            "name" : "serverId",
            "value" : "1"
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
          "name" : "database_host",
          "value" : "ip-10-1-2-181.ec2.internal"
        }, {
          "name" : "database_password",
          "value" : "Hue2017"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-00a66560ffc515da929b4cdb9fd07c10"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-44ce967d70921e570a07ccabfb001fd0",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "bf0e7020-ff48-440d-8012-1621ea6bf767"
          }, {
            "name" : "role_jceks_password",
            "value" : "b4ow9p64wm6kpgocm9zuq8zcv"
          }, {
            "name" : "secret_key",
            "value" : "1oT02EAtiCmjVXpvZdL6hYPTL2HcTL"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-44ce967d70921e570a07ccabfb001fd0",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6w3wxj28fd5wnoe6ghubnvy2w"
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
            "value" : "ip-10-1-2-181.ec2.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "Oozie2017"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
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
        "name" : "oozie-OOZIE_SERVER-44ce967d70921e570a07ccabfb001fd0",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1y2lgzy2ihf2yx96jkyfllubk"
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
            "value" : "9"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disk1/yarn/nm,/disk2/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disk1/yarn/container-logs,/disk2/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1620"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "9584"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6"
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
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "NPxHZaAGqVEhT9aLzS07Rvzqvuynnl"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-44ce967d70921e570a07ccabfb001fd0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9txz23omkv1werr7jhtb2h3hq"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9p0cdfos4slvbf03ozahckqpm"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c3978f40160696fadbc02822ef00c65a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a79m8jvujvmd93ye2s1xuqaz5"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5nbd3n553fhkjeh6r9hq9zyws"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "54"
          }, {
            "name" : "role_jceks_password",
            "value" : "9fi86djkrfgw7a68pwqd5kt7"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/disk1/dfs/dn,/disk2/dfs/dn"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
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
            "value" : "/disk2/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/disk1/dfs/nn,/disk2/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "6442450944"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/disk1/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "6442450944"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "elkZ4tyjw11IdAJMrdxyX6Q1NZMBj9"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "fOIPngMELpu7fbblxKm97RIb8QFlOW"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "Ei1GF9jQi6ZtMRPblhWureyjhK2SEu"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e6sj8u8blyd0yvinp5zitqxvm"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c3978f40160696fadbc02822ef00c65a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7gq293jqlf719hxmkdfuthfp6"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5haxkw6bya2lxkp75qwjd2hrt"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-c3978f40160696fadbc02822ef00c65a",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9t3djobpk7ddlrm1yxlfd05f1"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bpye7ia92fqjzcfez5d85qxf1"
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-44ce967d70921e570a07ccabfb001fd0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-HTTPFS-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6u3nv06vm6eyft4qopkxe52vg"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-00a66560ffc515da929b4cdb9fd07c10",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dbfv4z9qm2wixmzkelmo8m2p2"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c3978f40160696fadbc02822ef00c65a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "36t22lspedayn3ww6qyb8qf2r"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5wihaulo1p4dtak1712i8gsbp"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-c3978f40160696fadbc02822ef00c65a",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "HDFShaSEBC"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "HDFShaSEBC"
          }, {
            "name" : "namenode_id",
            "value" : "67"
          }, {
            "name" : "role_jceks_password",
            "value" : "dw8r65pc7br7n695lxuxb3p5v"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "HDFShaSEBC"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "HDFShaSEBC"
          }, {
            "name" : "namenode_id",
            "value" : "56"
          }, {
            "name" : "role_jceks_password",
            "value" : "8wgbk9hp240obzi0ltxs94dn8"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SENTRY_SERVER",
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-10-1-2-181.ec2.internal"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "Sentry2017"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,alexpg06"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-SENTRY_SERVER-c9fab83dca17fb36bcc1ff957da73319",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e98u8f7v4h73ptusonht13ch6"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "6d27949a-90df-4078-a590-70a8b42a8994",
    "ipAddress" : "10.1.2.132",
    "hostname" : "ip-10-1-2-132.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "c0f31fc5-ee7b-46e9-910f-1e2e9f11a477",
    "ipAddress" : "10.1.2.143",
    "hostname" : "ip-10-1-2-143.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "f91ebaeb-0410-4eb1-8bec-b4c14f087768",
    "ipAddress" : "10.1.2.176",
    "hostname" : "ip-10-1-2-176.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee",
    "ipAddress" : "10.1.2.181",
    "hostname" : "ip-10-1-2-181.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__0a535c38-386b-48f1-aff8-d602370e8584",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "02ea9a4631a6a36ad94e8faf092a6a9685a0b3c124917b2ced24014d16e6dfd2",
    "pwSalt" : 119939445643770858,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__c0e63919-f6a7-43e8-8cc3-3bcc85a18477",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6f68103e1b9a0386e8c1d863a08169a0b6ba8ea0e08b4818b5b86add5821aea1",
    "pwSalt" : 1360409157565102020,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-44ce967d70921e570a07ccabfb001fd0",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "c27f2e524446a7ce0f05bab15efdf814a5827ad50766fee0de0c6ccedb2ada88",
    "pwSalt" : -8560487868921663473,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-44ce967d70921e570a07ccabfb001fd0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ae78f3423fbb98c06f92a5108f4f70cefdbc3828b04eb3c4521bcd4c5ceb2ff7",
    "pwSalt" : 5369718926032085284,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-44ce967d70921e570a07ccabfb001fd0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "53b8c470e584a62d584af6c4fe71bb7bb8c0c6f665effa4cfe90ea643e469f9a",
    "pwSalt" : 7749602653650239793,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-44ce967d70921e570a07ccabfb001fd0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "952cd7937b6b5af3352bb0d6d40e2d97cd945444fd2e213a56dda2f322f350e0",
    "pwSalt" : -6235132122922831335,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-44ce967d70921e570a07ccabfb001fd0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ca4bc94f881a7776d32d32b5f9a0aaa46dd781f8d750efbf4a8ba06742d8ce8d",
    "pwSalt" : 4482963883528461405,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "218c5608472c2d792d8473c4e0eb760ac1ad3879d0491fe73029d8f84772bf09",
    "pwSalt" : 491283000005530515,
    "pwLogin" : true
  }, {
    "name" : "alexpg06",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "aa2e36648cc9231089554f96975548c4f790a2cc4fc28bb38d2f35062df914f9",
    "pwSalt" : -3829399780947799935,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "df43b68f261223d7f6389546ddb119a69ae829eb343a2e62309e57cb4a867770",
    "pwSalt" : 3195115617041508896,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.0",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20171002-1719",
    "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "6442450944"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-10-1-2-181.ec2.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "reports"
        }, {
          "name" : "headlamp_database_password",
          "value" : "Reports2017"
        }, {
          "name" : "headlamp_database_user",
          "value" : "reports"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "6442450944"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-44ce967d70921e570a07ccabfb001fd0",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1d77jidsu5520dyflxvbiyavs"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-44ce967d70921e570a07ccabfb001fd0",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7rnzmyedl823i51pui7ytrvu5"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-44ce967d70921e570a07ccabfb001fd0",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bki3gtg6ksjr75688gxiwn1xn"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-44ce967d70921e570a07ccabfb001fd0",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "a6fqddkqfl07zfjdhxxcvsc6u"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-44ce967d70921e570a07ccabfb001fd0",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "222a651f-df66-4b0d-91af-1467e4fec4ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1sek81l8rln2yw9uj725uh54x"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/25/2012 4:40"
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "ip-10-1-2-181.ec2.internal"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA/AAEADEFMRVhTRUJDLkNPTQAMY2xvdWRlcmEtc2NtAAAAAVoe8ZwBABcAEOiX/BhZDvIkN04fZL/YVbUAAAAB"
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@ALEXSEBC.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-10-1-2-181.ec2.internal"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "MAX_RENEW_LIFE",
      "value" : "604800"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "ALEXSEBC.COM"
    } ]
  }
}
