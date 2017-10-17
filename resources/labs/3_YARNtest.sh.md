# Modifications explained:

* Job was submited as user, that i previously created Mladen-Trampic-SRB-1989 linux/hdfs.
  * made small modification to write teragen / terasort output in my hdfs home dir.

* Changed loop to simulate multiple diferent requests.
  * added echoing to log time per operation.

started job with command:

```
 nohup bash YARNtest.sh 2>&1 | tee nohup.out &
``` 

## took a coffie, while it finishes. :)

```
#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 2 4 8    
do
   # Reducer containers
   for j in 1 2
   do                 
      # Container memory
      for k in 512 1024 
      do                         
         # Set mapper JVM heap 
         MAP_MB=`echo "($k*0.8)/1" | bc` 
         
         # Set reducer JVM heap 
         RED_MB=`echo "($k*0.8)/1" | bc` 
         echo "Configuration:"
         echo "-Dmapreduce.job.maps=$i"
         echo "-Dmapreduce.map.memory.mb=$k"
         echo "-Dmapreduce.map.java.opts.max.heap=$MAP_MB"
         echo "-Dmapreduce.reduce.java.opts.max.heap=$RED_MB"
         echo "-Dmapreduce.job.reduces=$j"
        echo ""
		echo ""
        echo "Teragen job starting:"
        echo ""
        time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     51200000 tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err                       
        echo "######################"
		echo "Teragen job finished!"
        echo "######################"
        echo ""
		echo ""
        echo "Terasort job starting:"
        time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
                 tg-10GB-${i}-${j}-${k}  \
                     ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err                         
        echo "######################"
        echo "Terasort job finished!"
        echo "######################"
        echo ""
        $HADOOP/hadoop fs -rm -r -skipTrash tg-10GB-${i}-${j}-${k}                         
		$HADOOP/hadoop fs -rm -r -skipTrash ts-10GB-${i}-${j}-${k}                 
        echo "ROUND FINISHED FOR SPECIFIED CONFIGURATION"
		echo ""
		echo ""
		done
   done
done

echo Testing loop ended on `date`
```