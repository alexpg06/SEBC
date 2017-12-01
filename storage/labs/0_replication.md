---
<div style="page-break-after: always;"></div>

# <center>HDFS Lab: Replicate to another cluster

<strong>1. Using distp</strong>
<pre class="prettyprint">
[centos@ip-10-1-2-181 ~]$ hadoop distcp hftp://ip-10-1-2-164.ec2.internal:50070/user/centos/source hdfs://10.1.2.143/user/centos/targeth/
17/11/29 00:57:21 INFO tools.OptionsParser: parseChunkSize: blocksperchunk false
17/11/29 00:57:22 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hftp://ip-10-1-2-164.ec2.internal:50070/user/centos/source], targetPath=hdfs://10.1.2.143/user/centos/targeth, targetPathExists=true, filtersFile='null', blocksPerChunk=0}
17/11/29 00:57:22 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-143.ec2.internal/10.1.2.143:8032
17/11/29 00:57:23 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 5; dirCnt = 2
17/11/29 00:57:23 INFO tools.SimpleCopyListing: Build file listing completed.
17/11/29 00:57:23 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/11/29 00:57:23 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/11/29 00:57:23 INFO tools.DistCp: Number of paths in the copy list: 5
17/11/29 00:57:23 INFO tools.DistCp: Number of paths in the copy list: 5
17/11/29 00:57:23 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-143.ec2.internal/10.1.2.143:8032
17/11/29 00:57:24 INFO mapreduce.JobSubmitter: number of splits:4
17/11/29 00:57:24 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911418851_0006
17/11/29 00:57:24 INFO impl.YarnClientImpl: Submitted application application_1511911418851_0006
17/11/29 00:57:24 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-143.ec2.internal:8088/proxy/application_1511911418851_0006/
17/11/29 00:57:24 INFO tools.DistCp: DistCp job-id: job_1511911418851_0006
17/11/29 00:57:24 INFO mapreduce.Job: Running job: job_1511911418851_0006
17/11/29 00:57:30 INFO mapreduce.Job: Job job_1511911418851_0006 running in uber mode : false
17/11/29 00:57:30 INFO mapreduce.Job:  map 0% reduce 0%
17/11/29 00:57:36 INFO mapreduce.Job:  map 25% reduce 0%
17/11/29 00:57:37 INFO mapreduce.Job:  map 50% reduce 0%
17/11/29 00:57:41 INFO mapreduce.Job:  map 100% reduce 0%
17/11/29 00:57:41 INFO mapreduce.Job: Job job_1511911418851_0006 completed successfully
17/11/29 00:57:41 INFO mapreduce.Job: Counters: 38
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=594624
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=2432
		HDFS: Number of bytes written=524288000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
		HFTP: Number of bytes read=0
		HFTP: Number of bytes written=0
		HFTP: Number of read operations=0
		HFTP: Number of large read operations=0
		HFTP: Number of write operations=0
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=26412
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=26412
		Total vcore-milliseconds taken by all map tasks=26412
		Total megabyte-milliseconds taken by all map tasks=27045888
	Map-Reduce Framework
		Map input records=5
		Map output records=0
		Input split bytes=464
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=197
		CPU time spent (ms)=13650
		Physical memory (bytes) snapshot=1007513600
		Virtual memory (bytes) snapshot=6404538368
		Total committed heap usage (bytes)=1862795264
	File Input Format Counters 
		Bytes Read=1968
	File Output Format Counters 
		Bytes Written=0
	DistCp Counters
		Bytes Copied=524288000
		Bytes Expected=524288000
		Files Copied=5
[centos@ip-10-1-2-181 ~]$ hadoop fs -du -h /user/centos/targeth
500 M  1.5 G  /user/centos/targeth/source
[centos@ip-10-1-2-181 ~]$ hadoop fs -du -h /user/centos/targeth/source
500 M  1.5 G  /user/centos/targeth/source/hugo
[centos@ip-10-1-2-181 ~]$ 
[centos@ip-10-1-2-181 ~]$ hdfs fsck /user/centos -files -blocks
Connecting to namenode via http://ip-10-1-2-143.ec2.internal:50070/fsck?ugi=centos&files=1&blocks=1&path=%2Fuser%2Fcentos
FSCK started by centos (auth:SIMPLE) from /10.1.2.181 for path /user/centos at Wed Nov 29 01:11:52 CST 2017
/user/centos <dir>
/user/centos/.staging <dir>
/user/centos/source <dir>
/user/centos/source/alexis <dir>
/user/centos/source/alexis/_SUCCESS 0 bytes, 0 block(s):  OK

/user/centos/source/alexis/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-1696625416-10.1.2.143-1511908888626:blk_1073745850_5026 len=134217728 Live_repl=3
1. BP-1696625416-10.1.2.143-1511908888626:blk_1073745852_5028 len=127926272 Live_repl=3

/user/centos/source/alexis/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-1696625416-10.1.2.143-1511908888626:blk_1073745851_5027 len=134217728 Live_repl=3
1. BP-1696625416-10.1.2.143-1511908888626:blk_1073745853_5029 len=127926272 Live_repl=3

/user/centos/target <dir>
/user/centos/target/source <dir>
/user/centos/target/source/diego <dir>
/user/centos/target/source/diego/_SUCCESS 0 bytes, 0 block(s):  OK

/user/centos/target/source/diego/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-1696625416-10.1.2.143-1511908888626:blk_1073745900_5076 len=134217728 Live_repl=3
1. BP-1696625416-10.1.2.143-1511908888626:blk_1073745904_5080 len=127926272 Live_repl=3

/user/centos/target/source/diego/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-1696625416-10.1.2.143-1511908888626:blk_1073745901_5077 len=134217728 Live_repl=3
1. BP-1696625416-10.1.2.143-1511908888626:blk_1073745903_5079 len=127926272 Live_repl=3

/user/centos/targeth <dir>
/user/centos/targeth/source <dir>
/user/centos/targeth/source/hugo <dir>
/user/centos/targeth/source/hugo/_SUCCESS 0 bytes, 0 block(s):  OK

/user/centos/targeth/source/hugo/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-1696625416-10.1.2.143-1511908888626:blk_1073745938_5114 len=134217728 Live_repl=3
1. BP-1696625416-10.1.2.143-1511908888626:blk_1073745940_5116 len=127926272 Live_repl=3

/user/centos/targeth/source/hugo/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-1696625416-10.1.2.143-1511908888626:blk_1073745939_5115 len=134217728 Live_repl=3
1. BP-1696625416-10.1.2.143-1511908888626:blk_1073745941_5117 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:	1572864000 B
 Total dirs:	10
 Total files:	9
 Total symlinks:		0
 Total blocks (validated):	12 (avg. block size 131072000 B)
 Minimally replicated blocks:	12 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Wed Nov 29 01:11:52 CST 2017 in 4 milliseconds


The filesystem under path '/user/centos' is HEALTHY
</pre>