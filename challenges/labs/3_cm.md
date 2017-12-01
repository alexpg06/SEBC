
# <center>Install CDH 5.9

<strong>1. ls /user</strong>
<pre class="prettyprint">
[hdfs@ip-10-1-2-173 ~]$ hdfs dfs -ls /user
Found 7 items
drwxr-xr-x   - haley  haley           0 2017-12-01 11:56 /user/haley
drwxrwxrwx   - mapred hadoop          0 2017-12-01 11:47 /user/history
drwxrwxr-t   - hive   hive            0 2017-12-01 11:48 /user/hive
drwxrwxr-x   - hue    hue             0 2017-12-01 11:49 /user/hue
drwxrwxr-x   - oozie  oozie           0 2017-12-01 11:49 /user/oozie
drwxr-xr-x   - saturn saturn          0 2017-12-01 11:56 /user/saturn
drwxr-x--x   - spark  spark           0 2017-12-01 11:48 /user/spark
</pre>

<strong>2. api/v14/hosts</strong>
<pre class="prettyprint">
[hdfs@ip-10-1-2-173 ~]$ curl -u admin:admin 'http://ec2-35-153-200-10.compute-1.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "2d715f04-222a-4810-adcc-56a7734d3e90",
    "ipAddress" : "10.1.2.155",
    "hostname" : "ip-10-1-2-155.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/hostRedirect/2d715f04-222a-4810-adcc-56a7734d3e90",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  }, {
    "hostId" : "a5c999ac-7726-4859-ac19-9330f1633929",
    "ipAddress" : "10.1.2.173",
    "hostname" : "ip-10-1-2-173.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/hostRedirect/a5c999ac-7726-4859-ac19-9330f1633929",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  }, {
    "hostId" : "62ea34e2-b678-422c-85af-5f4758e97972",
    "ipAddress" : "10.1.2.208",
    "hostname" : "ip-10-1-2-208.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/hostRedirect/62ea34e2-b678-422c-85af-5f4758e97972",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  }, {
    "hostId" : "f131657f-d51b-43b2-a165-c3cc6fef7124",
    "ipAddress" : "10.1.2.240",
    "hostname" : "ip-10-1-2-240.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/hostRedirect/f131657f-d51b-43b2-a165-c3cc6fef7124",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  } ]
}
</pre>

<strong>2. api/v8/clusters/alexpg06/services</strong>
<pre class="prettyprint">
[hdfs@ip-10-1-2-173 ~]$ curl -u admin:admin 'http://ec2-35-153-200-10.compute-1.amazonaws.com:7180/api/v8/clusters/alexpg06/services'
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-155.ec2.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}
</pre>
