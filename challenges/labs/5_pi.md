# Ejemplo PI

<pre class="prettyprint">
[haley@ip-10-1-2-173 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 16 1000
Number of Maps  = 16
Samples per Map = 1000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Starting Job
17/12/01 13:13:57 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-173.ec2.internal/10.1.2.173:8032
17/12/01 13:13:58 INFO hdfs.DFSClient: Created token for haley: HDFS_DELEGATION_TOKEN owner=haley@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512155638140, maxDate=1512760438140, sequenceNumber=1, masterKeyId=2 on 10.1.2.173:8020
17/12/01 13:13:58 INFO security.TokenCache: Got dt for hdfs://ip-10-1-2-173.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.2.173:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512155638140, maxDate=1512760438140, sequenceNumber=1, masterKeyId=2)
17/12/01 13:13:58 INFO input.FileInputFormat: Total input paths to process : 16
17/12/01 13:13:58 INFO mapreduce.JobSubmitter: number of splits:16
17/12/01 13:13:58 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154871096_0001
17/12/01 13:13:58 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.2.173:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@ALEXPG06.HQ, renewer=yarn, realUser=, issueDate=1512155638140, maxDate=1512760438140, sequenceNumber=1, masterKeyId=2)
17/12/01 13:13:59 INFO impl.YarnClientImpl: Submitted application application_1512154871096_0001
17/12/01 13:13:59 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-173.ec2.internal:8088/proxy/application_1512154871096_0001/
17/12/01 13:13:59 INFO mapreduce.Job: Running job: job_1512154871096_0001
17/12/01 13:14:08 INFO mapreduce.Job: Job job_1512154871096_0001 running in uber mode : false
17/12/01 13:14:08 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:14:14 INFO mapreduce.Job:  map 13% reduce 0%
17/12/01 13:14:23 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:14:29 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 13:14:29 INFO mapreduce.Job: Job job_1512154871096_0001 completed successfully
17/12/01 13:14:30 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=132
		FILE: Number of bytes written=2121819
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=4502
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=67
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters 
		Launched map tasks=16
		Launched reduce tasks=1
		Data-local map tasks=16
		Total time spent by all maps in occupied slots (ms)=189055
		Total time spent by all reduces in occupied slots (ms)=3128
		Total time spent by all map tasks (ms)=189055
		Total time spent by all reduce tasks (ms)=3128
		Total vcore-seconds taken by all map tasks=189055
		Total vcore-seconds taken by all reduce tasks=3128
		Total megabyte-seconds taken by all map tasks=193592320
		Total megabyte-seconds taken by all reduce tasks=3203072
	Map-Reduce Framework
		Map input records=16
		Map output records=32
		Map output bytes=288
		Map output materialized bytes=544
		Input split bytes=2614
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=544
		Reduce input records=32
		Reduce output records=0
		Spilled Records=64
		Shuffled Maps =16
		Failed Shuffles=0
		Merged Map outputs=16
		GC time elapsed (ms)=584
		CPU time spent (ms)=11770
		Physical memory (bytes) snapshot=8177414144
		Virtual memory (bytes) snapshot=27164094464
		Total committed heap usage (bytes)=8012693504
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=1888
	File Output Format Counters 
		Bytes Written=97
Job Finished in 32.119 seconds
Estimated value of Pi is 3.14250000000000000000

real	0m35.195s
user	0m5.136s
sys	0m0.283s
</pre>
