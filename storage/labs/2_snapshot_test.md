---
<div style="page-break-after: always;"></div>

# <center>HDFS Lab: Test HDFS snapshot
<pre class="prettyprint">[centos@ip-10-1-2-181 ~]$ hadoop fs -mkdir /user/centos/precious
[centos@ip-10-1-2-181 ~]$ hadoop fs -put SEBC-master.zip /user/centos/precious/
[centos@ip-10-1-2-181 ~]$ hadoop fs -rm -r -skipTrash /user/centos/precious
rm: The directory /user/centos/precious cannot be deleted since /user/centos/precious is snapshottable and already has snapshots
[centos@ip-10-1-2-181 ~]$ hadoop fs -rm -r -skipTrash /user/centos/precious/SEBC-master.zip
Deleted /user/centos/precious/SEBC-master.zip
[centos@ip-10-1-2-181 ~]$ exit
AlexMBP:sebc alexispadilla$ ./connectSEBC1.sh 
Agent pid 24855
Identity added: /Users/alexispadilla/sebc/asebc.pem (/Users/alexispadilla/sebc/asebc.pem)
Last login: Tue Nov 28 20:59:02 2017 from 189-213-92-109.static.axtel.net
[centos@ip-10-1-2-181 ~]$ hadoop fs -ls /user/centos/precious
Found 1 items
-rw-r--r--   3 hdfs centos     474833 2017-11-29 01:37 /user/centos/precious/SEBC-master.zip
[centos@ip-10-1-2-181 ~]$ 
</pre>