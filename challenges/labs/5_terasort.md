# <center>HDFS Lab: Test HDFS throughput

<strong>1. terasort</strong>
<pre class="prettyprint">
[saturn@ip-10-1-2-173 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort \
>  /user/saturn/ktgen /user/saturn/tsort
17/12/01 14:08:15 INFO terasort.TeraSort: starting
17/12/01 14:08:17 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512158897217, maxDate=1512763697217, sequenceNumber=6, masterKeyId=2 on 10.1.2.173:8020
17/12/01 14:08:17 INFO security.TokenCache: Got dt for hdfs://ip-10-1-2-173.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.2.173:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512158897217, maxDate=1512763697217, sequenceNumber=6, masterKeyId=2)
17/12/01 14:08:17 INFO input.FileInputFormat: Total input paths to process : 2
Spent 241ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 245ms
Sampling 8 splits of 8
Making 12 from 100000 sampled records
Computing parititions took 533ms
Spent 780ms computing partitions.
17/12/01 14:08:17 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-173.ec2.internal/10.1.2.173:8032
17/12/01 14:08:18 INFO mapreduce.JobSubmitter: number of splits:8
17/12/01 14:08:18 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154871096_0006
17/12/01 14:08:18 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.2.173:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512158897217, maxDate=1512763697217, sequenceNumber=6, masterKeyId=2)
17/12/01 14:08:18 INFO impl.YarnClientImpl: Submitted application application_1512154871096_0006
17/12/01 14:08:18 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-173.ec2.internal:8088/proxy/application_1512154871096_0006/
17/12/01 14:08:18 INFO mapreduce.Job: Running job: job_1512154871096_0006
17/12/01 14:08:26 INFO mapreduce.Job: Job job_1512154871096_0006 running in uber mode : false
17/12/01 14:08:26 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 14:08:37 INFO mapreduce.Job:  map 25% reduce 0%
17/12/01 14:08:38 INFO mapreduce.Job:  map 38% reduce 0%
17/12/01 14:08:42 INFO mapreduce.Job:  map 63% reduce 0%
17/12/01 14:08:43 INFO mapreduce.Job:  map 92% reduce 0%
17/12/01 14:08:44 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 14:08:52 INFO mapreduce.Job:  map 100% reduce 17%
17/12/01 14:08:55 INFO mapreduce.Job:  map 100% reduce 25%
17/12/01 14:08:56 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 14:08:57 INFO mapreduce.Job: Job job_1512154871096_0006 completed successfully
17/12/01 14:08:57 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=439891006
		FILE: Number of bytes written=879319114
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1000001072
		HDFS: Number of bytes written=1000000000
		HDFS: Number of read operations=60
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters 
		Launched map tasks=8
		Launched reduce tasks=12
		Data-local map tasks=7
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=100359
		Total time spent by all reduces in occupied slots (ms)=108710
		Total time spent by all map tasks (ms)=100359
		Total time spent by all reduce tasks (ms)=108710
		Total vcore-seconds taken by all map tasks=100359
		Total vcore-seconds taken by all reduce tasks=108710
		Total megabyte-seconds taken by all map tasks=102767616
		Total megabyte-seconds taken by all reduce tasks=111319040
	Map-Reduce Framework
		Map input records=10000000
		Map output records=10000000
		Map output bytes=1020000000
		Map output materialized bytes=436917382
		Input split bytes=1072
		Combine input records=0
		Combine output records=0
		Reduce input groups=10000000
		Reduce shuffle bytes=436917382
		Reduce input records=10000000
		Reduce output records=10000000
		Spilled Records=20000000
		Shuffled Maps =96
		Failed Shuffles=0
		Merged Map outputs=96
		GC time elapsed (ms)=1744
		CPU time spent (ms)=125040
		Physical memory (bytes) snapshot=8232095744
		Virtual memory (bytes) snapshot=32085254144
		Total committed heap usage (bytes)=11880366080
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=1000000000
	File Output Format Counters 
		Bytes Written=1000000000
17/12/01 14:08:57 INFO terasort.TeraSort: done

real	0m42.397s
user	0m6.787s
sys	0m0.317s
</pre>






