---
<div style="page-break-after: always;"></div>

# <center>HDFS Lab: Test HDFS throughput

<strong>1. teragen</strong>
<pre class="prettyprint">

[alexpg06@ip-10-1-2-181 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.12.1-1.cdh5.12.1.p0.3/jars/hadoop-examples.jar teragen -D dfs.block.size=33554432 -D mapreduce.job.maps=4 107374182 /user/alexpg06/teragen-output
17/11/28 23:54:23 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-143.ec2.internal/10.1.2.143:8032
17/11/28 23:54:24 INFO terasort.TeraGen: Generating 107374182 using 4
17/11/28 23:54:24 INFO mapreduce.JobSubmitter: number of splits:4
17/11/28 23:54:24 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/28 23:54:24 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911418851_0002
17/11/28 23:54:24 INFO impl.YarnClientImpl: Submitted application application_1511911418851_0002
17/11/28 23:54:24 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-143.ec2.internal:8088/proxy/application_1511911418851_0002/
17/11/28 23:54:24 INFO mapreduce.Job: Running job: job_1511911418851_0002
17/11/28 23:54:31 INFO mapreduce.Job: Job job_1511911418851_0002 running in uber mode : false
17/11/28 23:54:31 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 23:54:50 INFO mapreduce.Job:  map 4% reduce 0%
17/11/28 23:54:51 INFO mapreduce.Job:  map 14% reduce 0%
17/11/28 23:54:56 INFO mapreduce.Job:  map 18% reduce 0%
17/11/28 23:54:57 INFO mapreduce.Job:  map 21% reduce 0%
17/11/28 23:55:02 INFO mapreduce.Job:  map 25% reduce 0%
17/11/28 23:55:03 INFO mapreduce.Job:  map 26% reduce 0%
17/11/28 23:55:08 INFO mapreduce.Job:  map 27% reduce 0%
17/11/28 23:55:16 INFO mapreduce.Job:  map 28% reduce 0%
17/11/28 23:55:22 INFO mapreduce.Job:  map 30% reduce 0%
17/11/28 23:55:28 INFO mapreduce.Job:  map 33% reduce 0%
17/11/28 23:55:34 INFO mapreduce.Job:  map 37% reduce 0%
17/11/28 23:55:40 INFO mapreduce.Job:  map 39% reduce 0%
17/11/28 23:55:45 INFO mapreduce.Job:  map 43% reduce 0%
17/11/28 23:55:52 INFO mapreduce.Job:  map 45% reduce 0%
17/11/28 23:55:58 INFO mapreduce.Job:  map 49% reduce 0%
17/11/28 23:56:04 INFO mapreduce.Job:  map 53% reduce 0%
17/11/28 23:56:10 INFO mapreduce.Job:  map 56% reduce 0%
17/11/28 23:56:16 INFO mapreduce.Job:  map 60% reduce 0%
17/11/28 23:56:22 INFO mapreduce.Job:  map 63% reduce 0%
17/11/28 23:56:28 INFO mapreduce.Job:  map 65% reduce 0%
17/11/28 23:56:34 INFO mapreduce.Job:  map 69% reduce 0%
17/11/28 23:56:40 INFO mapreduce.Job:  map 74% reduce 0%
17/11/28 23:56:46 INFO mapreduce.Job:  map 76% reduce 0%
17/11/28 23:56:52 INFO mapreduce.Job:  map 78% reduce 0%
17/11/28 23:56:59 INFO mapreduce.Job:  map 82% reduce 0%
17/11/28 23:57:05 INFO mapreduce.Job:  map 89% reduce 0%
17/11/28 23:57:11 INFO mapreduce.Job:  map 91% reduce 0%
17/11/28 23:57:17 INFO mapreduce.Job:  map 92% reduce 0%
17/11/28 23:57:23 INFO mapreduce.Job:  map 96% reduce 0%
17/11/28 23:57:28 INFO mapreduce.Job:  map 97% reduce 0%
17/11/28 23:57:29 INFO mapreduce.Job:  map 100% reduce 0%
17/11/28 23:57:29 INFO mapreduce.Job: Job job_1511911418851_0002 completed successfully
17/11/28 23:57:29 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=581296
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=698872
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=698872
		Total vcore-milliseconds taken by all map tasks=698872
		Total megabyte-milliseconds taken by all map tasks=715644928
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1171
		CPU time spent (ms)=156180
		Physical memory (bytes) snapshot=694796288
		Virtual memory (bytes) snapshot=6357979136
		Total committed heap usage (bytes)=1542455296
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=230593859918397906
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10737418200

real	3m8.094s
user	0m5.301s
sys	0m0.303s
[alexpg06@ip-10-1-2-181 ~]$ hadoop fs -du -h /user/alexpg06
0       0       /user/alexpg06/.staging
10.0 G  30.0 G  /user/alexpg06/teragen-output
</pre>



<strong>1. terasort</strong>
<pre class="prettyprint">

[alexpg06@ip-10-1-2-181 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.12.1-1.cdh5.12.1.p0.3/jars/hadoop-examples.jar terasort /user/alexpg06/teragen-output /user/alexpg06/terasort-output
17/11/29 00:03:00 INFO terasort.TeraSort: starting
17/11/29 00:03:02 INFO input.FileInputFormat: Total input paths to process : 4
Spent 245ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 251ms
Sampling 10 splits of 320
Making 12 from 100000 sampled records
Computing parititions took 599ms
Spent 853ms computing partitions.
17/11/29 00:03:02 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-143.ec2.internal/10.1.2.143:8032
17/11/29 00:03:03 INFO mapreduce.JobSubmitter: number of splits:320
17/11/29 00:03:03 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911418851_0003
17/11/29 00:03:03 INFO impl.YarnClientImpl: Submitted application application_1511911418851_0003
17/11/29 00:03:03 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-143.ec2.internal:8088/proxy/application_1511911418851_0003/
17/11/29 00:03:03 INFO mapreduce.Job: Running job: job_1511911418851_0003
17/11/29 00:03:09 INFO mapreduce.Job: Job job_1511911418851_0003 running in uber mode : false
17/11/29 00:03:09 INFO mapreduce.Job:  map 0% reduce 0%
17/11/29 00:03:16 INFO mapreduce.Job:  map 1% reduce 0%
17/11/29 00:03:19 INFO mapreduce.Job:  map 2% reduce 0%
17/11/29 00:03:22 INFO mapreduce.Job:  map 3% reduce 0%
17/11/29 00:03:24 INFO mapreduce.Job:  map 5% reduce 0%
17/11/29 00:03:28 INFO mapreduce.Job:  map 7% reduce 0%
17/11/29 00:03:29 INFO mapreduce.Job:  map 8% reduce 0%
17/11/29 00:03:38 INFO mapreduce.Job:  map 10% reduce 0%
17/11/29 00:03:39 INFO mapreduce.Job:  map 12% reduce 0%
17/11/29 00:03:41 INFO mapreduce.Job:  map 13% reduce 0%
17/11/29 00:03:47 INFO mapreduce.Job:  map 14% reduce 0%
17/11/29 00:03:48 INFO mapreduce.Job:  map 15% reduce 0%
17/11/29 00:03:53 INFO mapreduce.Job:  map 18% reduce 0%
17/11/29 00:03:56 INFO mapreduce.Job:  map 19% reduce 0%
17/11/29 00:03:57 INFO mapreduce.Job:  map 20% reduce 0%
17/11/29 00:04:03 INFO mapreduce.Job:  map 21% reduce 0%
17/11/29 00:04:05 INFO mapreduce.Job:  map 22% reduce 0%
17/11/29 00:04:06 INFO mapreduce.Job:  map 24% reduce 0%
17/11/29 00:04:07 INFO mapreduce.Job:  map 25% reduce 0%
17/11/29 00:04:11 INFO mapreduce.Job:  map 26% reduce 0%
17/11/29 00:04:14 INFO mapreduce.Job:  map 27% reduce 0%
17/11/29 00:04:15 INFO mapreduce.Job:  map 28% reduce 0%
17/11/29 00:04:20 INFO mapreduce.Job:  map 30% reduce 0%
17/11/29 00:04:22 INFO mapreduce.Job:  map 31% reduce 0%
17/11/29 00:04:23 INFO mapreduce.Job:  map 32% reduce 0%
17/11/29 00:04:27 INFO mapreduce.Job:  map 33% reduce 0%
17/11/29 00:04:30 INFO mapreduce.Job:  map 34% reduce 0%
17/11/29 00:04:33 INFO mapreduce.Job:  map 36% reduce 0%
17/11/29 00:04:35 INFO mapreduce.Job:  map 38% reduce 0%
17/11/29 00:04:40 INFO mapreduce.Job:  map 39% reduce 0%
17/11/29 00:04:41 INFO mapreduce.Job:  map 40% reduce 0%
17/11/29 00:04:44 INFO mapreduce.Job:  map 41% reduce 0%
17/11/29 00:04:47 INFO mapreduce.Job:  map 42% reduce 0%
17/11/29 00:04:48 INFO mapreduce.Job:  map 43% reduce 0%
17/11/29 00:04:49 INFO mapreduce.Job:  map 44% reduce 0%
17/11/29 00:04:51 INFO mapreduce.Job:  map 45% reduce 0%
17/11/29 00:04:53 INFO mapreduce.Job:  map 46% reduce 0%
17/11/29 00:04:58 INFO mapreduce.Job:  map 47% reduce 0%
17/11/29 00:05:00 INFO mapreduce.Job:  map 48% reduce 0%
17/11/29 00:05:01 INFO mapreduce.Job:  map 49% reduce 0%
17/11/29 00:05:02 INFO mapreduce.Job:  map 50% reduce 0%
17/11/29 00:05:05 INFO mapreduce.Job:  map 51% reduce 0%
17/11/29 00:05:06 INFO mapreduce.Job:  map 52% reduce 0%
17/11/29 00:05:10 INFO mapreduce.Job:  map 53% reduce 0%
17/11/29 00:05:12 INFO mapreduce.Job:  map 54% reduce 0%
17/11/29 00:05:15 INFO mapreduce.Job:  map 56% reduce 0%
17/11/29 00:05:17 INFO mapreduce.Job:  map 57% reduce 0%
17/11/29 00:05:18 INFO mapreduce.Job:  map 58% reduce 0%
17/11/29 00:05:24 INFO mapreduce.Job:  map 60% reduce 0%
17/11/29 00:05:28 INFO mapreduce.Job:  map 61% reduce 0%
17/11/29 00:05:29 INFO mapreduce.Job:  map 62% reduce 0%
17/11/29 00:05:30 INFO mapreduce.Job:  map 63% reduce 0%
17/11/29 00:05:32 INFO mapreduce.Job:  map 64% reduce 0%
17/11/29 00:05:36 INFO mapreduce.Job:  map 65% reduce 0%
17/11/29 00:05:37 INFO mapreduce.Job:  map 66% reduce 0%
17/11/29 00:05:38 INFO mapreduce.Job:  map 67% reduce 0%
17/11/29 00:05:42 INFO mapreduce.Job:  map 68% reduce 0%
17/11/29 00:05:44 INFO mapreduce.Job:  map 69% reduce 0%
17/11/29 00:05:45 INFO mapreduce.Job:  map 70% reduce 0%
17/11/29 00:05:47 INFO mapreduce.Job:  map 71% reduce 0%
17/11/29 00:05:51 INFO mapreduce.Job:  map 72% reduce 0%
17/11/29 00:05:54 INFO mapreduce.Job:  map 74% reduce 0%
17/11/29 00:05:55 INFO mapreduce.Job:  map 75% reduce 0%
17/11/29 00:05:57 INFO mapreduce.Job:  map 76% reduce 0%
17/11/29 00:06:00 INFO mapreduce.Job:  map 77% reduce 0%
17/11/29 00:06:04 INFO mapreduce.Job:  map 78% reduce 0%
17/11/29 00:06:05 INFO mapreduce.Job:  map 79% reduce 0%
17/11/29 00:06:08 INFO mapreduce.Job:  map 80% reduce 0%
17/11/29 00:06:09 INFO mapreduce.Job:  map 81% reduce 0%
17/11/29 00:06:11 INFO mapreduce.Job:  map 82% reduce 0%
17/11/29 00:06:12 INFO mapreduce.Job:  map 83% reduce 0%
17/11/29 00:06:17 INFO mapreduce.Job:  map 84% reduce 0%
17/11/29 00:06:18 INFO mapreduce.Job:  map 85% reduce 0%
17/11/29 00:06:23 INFO mapreduce.Job:  map 86% reduce 0%
17/11/29 00:06:27 INFO mapreduce.Job:  map 87% reduce 0%
17/11/29 00:06:28 INFO mapreduce.Job:  map 87% reduce 5%
17/11/29 00:06:29 INFO mapreduce.Job:  map 87% reduce 7%
17/11/29 00:06:31 INFO mapreduce.Job:  map 87% reduce 10%
17/11/29 00:06:32 INFO mapreduce.Job:  map 87% reduce 17%
17/11/29 00:06:33 INFO mapreduce.Job:  map 88% reduce 17%
17/11/29 00:06:37 INFO mapreduce.Job:  map 89% reduce 17%
17/11/29 00:06:39 INFO mapreduce.Job:  map 89% reduce 20%
17/11/29 00:06:41 INFO mapreduce.Job:  map 90% reduce 20%
17/11/29 00:06:45 INFO mapreduce.Job:  map 91% reduce 20%
17/11/29 00:06:47 INFO mapreduce.Job:  map 92% reduce 20%
17/11/29 00:06:54 INFO mapreduce.Job:  map 93% reduce 20%
17/11/29 00:06:56 INFO mapreduce.Job:  map 94% reduce 20%
17/11/29 00:06:57 INFO mapreduce.Job:  map 94% reduce 21%
17/11/29 00:07:01 INFO mapreduce.Job:  map 95% reduce 21%
17/11/29 00:07:04 INFO mapreduce.Job:  map 96% reduce 21%
17/11/29 00:07:06 INFO mapreduce.Job:  map 97% reduce 21%
17/11/29 00:07:11 INFO mapreduce.Job:  map 97% reduce 22%
17/11/29 00:07:12 INFO mapreduce.Job:  map 98% reduce 22%
17/11/29 00:07:14 INFO mapreduce.Job:  map 99% reduce 22%
17/11/29 00:07:19 INFO mapreduce.Job:  map 100% reduce 22%
17/11/29 00:07:22 INFO mapreduce.Job:  map 100% reduce 23%
17/11/29 00:07:23 INFO mapreduce.Job:  map 100% reduce 26%
17/11/29 00:07:25 INFO mapreduce.Job:  map 100% reduce 29%
17/11/29 00:07:26 INFO mapreduce.Job:  map 100% reduce 31%
17/11/29 00:07:27 INFO mapreduce.Job:  map 100% reduce 37%
17/11/29 00:07:28 INFO mapreduce.Job:  map 100% reduce 43%
17/11/29 00:07:29 INFO mapreduce.Job:  map 100% reduce 54%
17/11/29 00:07:31 INFO mapreduce.Job:  map 100% reduce 58%
17/11/29 00:07:32 INFO mapreduce.Job:  map 100% reduce 63%
17/11/29 00:07:33 INFO mapreduce.Job:  map 100% reduce 69%
17/11/29 00:07:34 INFO mapreduce.Job:  map 100% reduce 72%
17/11/29 00:07:35 INFO mapreduce.Job:  map 100% reduce 75%
17/11/29 00:07:37 INFO mapreduce.Job:  map 100% reduce 79%
17/11/29 00:07:38 INFO mapreduce.Job:  map 100% reduce 82%
17/11/29 00:07:39 INFO mapreduce.Job:  map 100% reduce 87%
17/11/29 00:07:40 INFO mapreduce.Job:  map 100% reduce 89%
17/11/29 00:07:41 INFO mapreduce.Job:  map 100% reduce 90%
17/11/29 00:07:43 INFO mapreduce.Job:  map 100% reduce 91%
17/11/29 00:07:44 INFO mapreduce.Job:  map 100% reduce 92%
17/11/29 00:07:45 INFO mapreduce.Job:  map 100% reduce 93%
17/11/29 00:07:48 INFO mapreduce.Job:  map 100% reduce 94%
17/11/29 00:07:49 INFO mapreduce.Job:  map 100% reduce 95%
17/11/29 00:07:50 INFO mapreduce.Job:  map 100% reduce 96%
17/11/29 00:07:55 INFO mapreduce.Job:  map 100% reduce 97%
17/11/29 00:07:56 INFO mapreduce.Job:  map 100% reduce 100%
17/11/29 00:07:56 INFO mapreduce.Job: Job job_1511911418851_0003 completed successfully
17/11/29 00:07:56 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4770006882
		FILE: Number of bytes written=9481791908
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10737464600
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=996
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters 
		Launched map tasks=320
		Launched reduce tasks=12
		Data-local map tasks=320
		Total time spent by all maps in occupied slots (ms)=2817241
		Total time spent by all reduces in occupied slots (ms)=899218
		Total time spent by all map tasks (ms)=2817241
		Total time spent by all reduce tasks (ms)=899218
		Total vcore-milliseconds taken by all map tasks=2817241
		Total vcore-milliseconds taken by all reduce tasks=899218
		Total megabyte-milliseconds taken by all map tasks=2884854784
		Total megabyte-milliseconds taken by all reduce tasks=920799232
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Map output bytes=10952166564
		Map output materialized bytes=4662963282
		Input split bytes=46400
		Combine input records=0
		Combine output records=0
		Reduce input groups=107374182
		Reduce shuffle bytes=4662963282
		Reduce input records=107374182
		Reduce output records=107374182
		Spilled Records=214748364
		Shuffled Maps =3840
		Failed Shuffles=0
		Merged Map outputs=3840
		GC time elapsed (ms)=31053
		CPU time spent (ms)=1663660
		Physical memory (bytes) snapshot=175305576448
		Virtual memory (bytes) snapshot=530606542848
		Total committed heap usage (bytes)=169890807808
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10737418200
	File Output Format Counters 
		Bytes Written=10737418200
17/11/29 00:07:56 INFO terasort.TeraSort: done

real	4m56.834s
user	0m8.485s
sys	0m0.415s
[alexpg06@ip-10-1-2-181 ~]$ hadoop fs -du -h /user/alexpg06
0       0       /user/alexpg06/.staging
10.0 G  30.0 G  /user/alexpg06/teragen-output
10.0 G  10.0 G  /user/alexpg06/terasort-output
[alexpg06@ip-10-1-2-181 ~]$ 

</pre>