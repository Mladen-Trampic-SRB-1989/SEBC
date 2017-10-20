* Run the terasort program as ernest using /user/ernest/tgen512m
  * Command :
  ```
   [ernest@ip-172-31-34-39 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-mapreduce-examples-2.6.0-cdh*.jar terasort tgen512m tsort512m
  ```
  * Output:
  ```
   17/10/20 10:14:06 INFO mapreduce.Job: Job job_1508493587968_0005 completed successfully
   17/10/20 10:14:07 INFO mapreduce.Job: Counters: 50
           File System Counters
                   FILE: Number of bytes read=2269669922
                   FILE: Number of bytes written=4513839845
                   FILE: Number of read operations=0
                   FILE: Number of large read operations=0
                   FILE: Number of write operations=0
                   HDFS: Number of bytes read=5120023868
                   HDFS: Number of bytes written=5120000000
                   HDFS: Number of read operations=492
                   HDFS: Number of large read operations=0
                   HDFS: Number of write operations=16
           Job Counters
                   Killed reduce tasks=3
                   Launched map tasks=156
                   Launched reduce tasks=11
                   Data-local map tasks=156
                   Total time spent by all maps in occupied slots (ms)=1143749
                   Total time spent by all reduces in occupied slots (ms)=378118
                   Total time spent by all map tasks (ms)=1143749
                   Total time spent by all reduce tasks (ms)=378118
                   Total vcore-seconds taken by all map tasks=1143749
                   Total vcore-seconds taken by all reduce tasks=378118
                   Total megabyte-seconds taken by all map tasks=1171198976
                   Total megabyte-seconds taken by all reduce tasks=387192832
           Map-Reduce Framework
                   Map input records=51200000
                   Map output records=51200000
                   Map output bytes=5222400000
                   Map output materialized bytes=2223514105
                   Input split bytes=23868
                   Combine input records=0
                   Combine output records=0
                   Reduce input groups=51200000
                   Reduce shuffle bytes=2223514105
                   Reduce input records=51200000
                   Reduce output records=51200000
                   Spilled Records=102400000
                   Shuffled Maps =1248
                   Failed Shuffles=0
                   Merged Map outputs=1248
                   GC time elapsed (ms)=29370
                   CPU time spent (ms)=822180
                   Physical memory (bytes) snapshot=79840702464
                   Virtual memory (bytes) snapshot=456855740416
                   Total committed heap usage (bytes)=82154356736
           Shuffle Errors
                   BAD_ID=0
                   CONNECTION=0
                   IO_ERROR=0
                   WRONG_LENGTH=0
                   WRONG_MAP=0
                   WRONG_REDUCE=0
           File Input Format Counters
                   Bytes Read=5120000000
           File Output Format Counters
                   Bytes Written=5120000000
   17/10/20 10:14:07 INFO terasort.TeraSort: done
   
   real    4m2.520s
   user    0m10.974s
   sys     0m0.432s
  ```