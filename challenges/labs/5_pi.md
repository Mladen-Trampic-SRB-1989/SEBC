* Run the Hadoop pi program as the user siwicki
  * Command:
  ```
   [siwicki@ip-172-31-43-139 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 10 100 | tee siwickiPi.log
  ```
  * Output:
  ```
   17/10/20 10:13:43 INFO mapreduce.Job: Job job_1508493587968_0006 completed successfully
   17/10/20 10:13:43 INFO mapreduce.Job: Counters: 50
           File System Counters
                   FILE: Number of bytes read=95
                   FILE: Number of bytes written=1377129
                   FILE: Number of read operations=0
                   FILE: Number of large read operations=0
                   FILE: Number of write operations=0
                   HDFS: Number of bytes read=2990
                   HDFS: Number of bytes written=215
                   HDFS: Number of read operations=43
                   HDFS: Number of large read operations=0
                   HDFS: Number of write operations=3
           Job Counters
                   Launched map tasks=10
                   Launched reduce tasks=1
                   Data-local map tasks=9
                   Rack-local map tasks=1
                   Total time spent by all maps in occupied slots (ms)=58860
                   Total time spent by all reduces in occupied slots (ms)=4463
                   Total time spent by all map tasks (ms)=58860
                   Total time spent by all reduce tasks (ms)=4463
                   Total vcore-seconds taken by all map tasks=58860
                   Total vcore-seconds taken by all reduce tasks=4463
                   Total megabyte-seconds taken by all map tasks=60272640
                   Total megabyte-seconds taken by all reduce tasks=4570112
           Map-Reduce Framework
                   Map input records=10
                   Map output records=20
                   Map output bytes=180
                   Map output materialized bytes=340
                   Input split bytes=1810
                   Combine input records=0
                   Combine output records=0
                   Reduce input groups=2
                   Reduce shuffle bytes=340
                   Reduce input records=20
                   Reduce output records=0
                   Spilled Records=40
                   Shuffled Maps =10
                   Failed Shuffles=0
                   Merged Map outputs=10
                   GC time elapsed (ms)=1108
                   CPU time spent (ms)=7780
                   Physical memory (bytes) snapshot=4617887744
                   Virtual memory (bytes) snapshot=30645968896
                   Total committed heap usage (bytes)=4675600384
           Shuffle Errors
                   BAD_ID=0
                   CONNECTION=0
                   IO_ERROR=0
                   WRONG_LENGTH=0
                   WRONG_MAP=0
                   WRONG_REDUCE=0
           File Input Format Counters
                   Bytes Read=1180
           File Output Format Counters
                   Bytes Written=97
   Job Finished in 43.029 seconds
   Estimated value of Pi is 3.14800000000000000000
   
   real    0m54.708s
   user    0m8.991s
   sys     0m0.479s
  ```