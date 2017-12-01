# <center>HDFS Testing

* <strong>1. teragen and time Output</strong>
<pre class="prettyprint">
[saturn@ip-10-1-2-173 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen \
> -D dfs.block.size=33554432 \
> -D mapreduce.map.memory.mb=512 \
> -D mapreduce.job.maps=12 \
> 65536000 /user/saturn/tgen
17/12/01 13:52:45 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-173.ec2.internal/10.1.2.173:8032
17/12/01 13:52:45 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512157965725, maxDate=1512762765725, sequenceNumber=4, masterKeyId=2 on 10.1.2.173:8020
17/12/01 13:52:45 INFO security.TokenCache: Got dt for hdfs://ip-10-1-2-173.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.2.173:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512157965725, maxDate=1512762765725, sequenceNumber=4, masterKeyId=2)
17/12/01 13:52:46 INFO terasort.TeraSort: Generating 65536000 using 12
17/12/01 13:52:46 INFO mapreduce.JobSubmitter: number of splits:12
17/12/01 13:52:46 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 13:52:46 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154871096_0004
17/12/01 13:52:46 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.2.173:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512157965725, maxDate=1512762765725, sequenceNumber=4, masterKeyId=2)
17/12/01 13:52:46 INFO impl.YarnClientImpl: Submitted application application_1512154871096_0004
17/12/01 13:52:46 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-173.ec2.internal:8088/proxy/application_1512154871096_0004/
17/12/01 13:52:46 INFO mapreduce.Job: Running job: job_1512154871096_0004
17/12/01 13:52:53 INFO mapreduce.Job: Job job_1512154871096_0004 running in uber mode : false
17/12/01 13:52:53 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:53:04 INFO mapreduce.Job:  map 11% reduce 0%
17/12/01 13:53:08 INFO mapreduce.Job:  map 15% reduce 0%
17/12/01 13:53:10 INFO mapreduce.Job:  map 17% reduce 0%
17/12/01 13:53:12 INFO mapreduce.Job:  map 27% reduce 0%
17/12/01 13:53:13 INFO mapreduce.Job:  map 29% reduce 0%
17/12/01 13:53:14 INFO mapreduce.Job:  map 30% reduce 0%
17/12/01 13:53:15 INFO mapreduce.Job:  map 34% reduce 0%
17/12/01 13:53:16 INFO mapreduce.Job:  map 35% reduce 0%
17/12/01 13:53:18 INFO mapreduce.Job:  map 40% reduce 0%
17/12/01 13:53:19 INFO mapreduce.Job:  map 41% reduce 0%
17/12/01 13:53:21 INFO mapreduce.Job:  map 44% reduce 0%
17/12/01 13:53:22 INFO mapreduce.Job:  map 45% reduce 0%
17/12/01 13:53:24 INFO mapreduce.Job:  map 46% reduce 0%
17/12/01 13:53:33 INFO mapreduce.Job:  map 49% reduce 0%
17/12/01 13:53:34 INFO mapreduce.Job:  map 51% reduce 0%
17/12/01 13:53:42 INFO mapreduce.Job:  map 54% reduce 0%
17/12/01 13:53:43 INFO mapreduce.Job:  map 56% reduce 0%
17/12/01 13:53:45 INFO mapreduce.Job:  map 58% reduce 0%
17/12/01 13:53:46 INFO mapreduce.Job:  map 59% reduce 0%
17/12/01 13:53:48 INFO mapreduce.Job:  map 61% reduce 0%
17/12/01 13:53:49 INFO mapreduce.Job:  map 62% reduce 0%
17/12/01 13:53:51 INFO mapreduce.Job:  map 63% reduce 0%
17/12/01 13:53:52 INFO mapreduce.Job:  map 64% reduce 0%
17/12/01 13:53:54 INFO mapreduce.Job:  map 66% reduce 0%
17/12/01 13:53:55 INFO mapreduce.Job:  map 67% reduce 0%
17/12/01 13:53:57 INFO mapreduce.Job:  map 69% reduce 0%
17/12/01 13:53:58 INFO mapreduce.Job:  map 71% reduce 0%
17/12/01 13:54:00 INFO mapreduce.Job:  map 72% reduce 0%
17/12/01 13:54:01 INFO mapreduce.Job:  map 74% reduce 0%
17/12/01 13:54:03 INFO mapreduce.Job:  map 76% reduce 0%
17/12/01 13:54:04 INFO mapreduce.Job:  map 78% reduce 0%
17/12/01 13:54:06 INFO mapreduce.Job:  map 80% reduce 0%
17/12/01 13:54:07 INFO mapreduce.Job:  map 82% reduce 0%
17/12/01 13:54:09 INFO mapreduce.Job:  map 84% reduce 0%
17/12/01 13:54:10 INFO mapreduce.Job:  map 86% reduce 0%
17/12/01 13:54:12 INFO mapreduce.Job:  map 88% reduce 0%
17/12/01 13:54:13 INFO mapreduce.Job:  map 90% reduce 0%
17/12/01 13:54:15 INFO mapreduce.Job:  map 93% reduce 0%
17/12/01 13:54:16 INFO mapreduce.Job:  map 97% reduce 0%
17/12/01 13:54:18 INFO mapreduce.Job:  map 98% reduce 0%
17/12/01 13:54:19 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:54:30 INFO mapreduce.Job: Job job_1512154871096_0004 completed successfully
17/12/01 13:54:30 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1489334
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1025
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters 
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=961522
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=961522
		Total vcore-seconds taken by all map tasks=961522
		Total megabyte-seconds taken by all map tasks=984598528
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1871
		CPU time spent (ms)=146750
		Physical memory (bytes) snapshot=2415583232
		Virtual memory (bytes) snapshot=13701210112
		Total committed heap usage (bytes)=4461166592
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

real	1m47.540s
user	0m5.600s
sys	0m0.328s
</pre>

* <strong>2. hdfs dfs -ls /user/saturn/tgen</strong>
<pre class="prettyprint">
[saturn@ip-10-1-2-173 ~]$ hadoop fs -ls -h /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn saturn          0 2017-12-01 13:54 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:53 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:53 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn saturn    520.8 M 2017-12-01 13:54 /user/saturn/tgen/part-m-00011
</pre>

* <strong>3. hadoop fsck -blocks /user/saturn</strong>
<pre class="prettyprint">
[saturn@ip-10-1-2-173 ~]$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-10-1-2-173.ec2.internal:50070
FSCK started by saturn (auth:KERBEROS_SSL) from /10.1.2.173 for path /user/saturn at Fri Dec 01 13:58:48 CST 2017
.............Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	3
 Total files:	13
 Total symlinks:		0
 Total blocks (validated):	204 (avg. block size 32125490 B)
 Minimally replicated blocks:	204 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Fri Dec 01 13:58:48 CST 2017 in 11 milliseconds


The filesystem under path '/user/saturn' is HEALTHY
</pre>

