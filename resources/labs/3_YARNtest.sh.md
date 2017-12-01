#!/bin/sh
# Confirm the path values given below correspond to your installation

HADOOP=/opt/cloudera/parcels/CDH/bin
# MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
MR=/opt/cloudera/parcels/CDH/jars

# Mark start of the loop
echo Testing loop started on `date`
echo " "

# Mapper containers
for i in 32   
do
   # Reducer containers
   for j in 4
   do                 
      # Container memory
      for k in 2048 4096
      do                         
         # Set mapper JVM heap 
         MAP_MB=`echo "($k*0.8)/1" | bc` 

         # Set reducer JVM heap 
         RED_MB=`echo "($k*0.8)/1" | bc`
        
        echo " "
        echo "*PARAMETER VALUES*"
        echo "-Dmapreduce.job.maps=$i"
        echo "-Dmapreduce.job.reduces=$j"
        echo "-Dmapreduce.map.memory.mb=$k"
        echo "-Dmapreduce.map.java.opts.max.heap=$MAP_MB"
        echo "-Dmapreduce.reduce.memory.mb=$k"
        echo "-Dmapreduce.reduce.java.opts.max.heap=$RED_MB"
        
        time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -D mapreduce.job.maps=$i \
                     -D mapreduce.map.memory.mb=$k \
                     -D mapreduce.map.java.opts.max.heap=$MAP_MB \
                     51200000 /user/centos/results/tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err                      

        time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
                     -D mapreduce.job.maps=$i \
                     -D mapreduce.job.reduces=$j \
                     -D mapreduce.map.memory.mb=$k \
                     -D mapreduce.map.java.opts.max.heap=$MAP_MB \
                     -D mapreduce.reduce.memory.mb=$k \
                     -D mapreduce.reduce.java.opts.max.heap=$RED_MB \
	             	 /user/centos/results/tg-10GB-${i}-${j}-${k}  \
                     /user/centos/results/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err                     


        $HADOOP/hadoop fs -rm -r -skipTrash /user/centos/results/tg-10GB-${i}-${j}-${k}                         
        $HADOOP/hadoop fs -rm -r -skipTrash /user/centos/results/ts-10GB-${i}-${j}-${k}                 
      done
   done
done

echo Testing loop ended on `date`
