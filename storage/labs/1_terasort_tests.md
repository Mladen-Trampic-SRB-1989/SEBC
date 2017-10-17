* Create an end-user Linux account named with your GitHub handle
  * Behavior replicated on every Node in Cluster
  ```
   [root@ip-172-31-42-124 ~]# groupadd -g 1001 Mladen-Trampic-SRB-1989
   [root@ip-172-31-42-124 ~]# adduser -u 1001 -g 1001 Mladen-Trampic-SRB-1989
  ```
  * Create a home HDFS directory for this user as well
    * This has been done in previous exercise, but directory can be created with following:
    ```
     HADOOP_USER_NAME=hdfs hdfs dfs -mkdir /user/Mladen-Trampic-SRB-1989
     HADOOP_USER_NAME=hdfs hdfs dfs -chown -R Mladen-Trampic-SRB-1989:Mladen-Trampic-SRB-1989 /user/Mladen-Trampic-SRB-1989
    ```

* Create a 10 GB file using teragen
  * Set the number of mappers to four
  ```
   -D mapreduce.job.maps=4
  ```
  * Limit the block size to 32 MB
  ```
   -D dfs.block.size=33554432
  ```
  * Land the result under your user's home directory
  ```
   Output HDFS directory is: hdfs_testing like filename on github
   Since i am running as user Mladen-Trampic-SRB-1989, specifying relative path will do the job.
  ```
  * Use the time command to report the job's duration
   * Final command with time:
   ```
    [Mladen-Trampic-SRB-1989@ip-172-31-42-124 ~]$ time hadoop jar \
    /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-mapreduce-examples-2.6.0-cdh5.8.3.jar \
    teragen \
    -D dfs.block.size=33554432 \
    -D mapreduce.job.maps=4 \
    107374183 \
    hdfs_testing
   ```
   
  * Output of Command:
  ```
   17/10/17 12:00:06 INFO mapreduce.Job: Job job_1508186980909_0003 completed successfully
   17/10/17 12:00:06 INFO mapreduce.Job: Counters: 31
           File System Counters
                   FILE: Number of bytes read=0
                   FILE: Number of bytes written=489564
                   FILE: Number of read operations=0
                   FILE: Number of large read operations=0
                   FILE: Number of write operations=0
                   HDFS: Number of bytes read=344
                   HDFS: Number of bytes written=10737418300
                   HDFS: Number of read operations=16
                   HDFS: Number of large read operations=0
                   HDFS: Number of write operations=8
           Job Counters
                   Launched map tasks=4
                   Other local map tasks=4
                   Total time spent by all maps in occupied slots (ms)=210031
                   Total time spent by all reduces in occupied slots (ms)=0
                   Total time spent by all map tasks (ms)=210031
                   Total vcore-seconds taken by all map tasks=210031
                   Total megabyte-seconds taken by all map tasks=215071744
           Map-Reduce Framework
                   Map input records=107374183
                   Map output records=107374183
                   Input split bytes=344
                   Spilled Records=0
                   Failed Shuffles=0
                   Merged Map outputs=0
                   GC time elapsed (ms)=1364
                   CPU time spent (ms)=178270
                   Physical memory (bytes) snapshot=765927424
                   Virtual memory (bytes) snapshot=6312271872
                   Total committed heap usage (bytes)=936378368
           org.apache.hadoop.examples.terasort.TeraGen$Counters
                   CHECKSUM=230593860607047066
           File Input Format Counters
                   Bytes Read=0
           File Output Format Counters
                   Bytes Written=10737418300
   
   real    1m4.709s
   user    0m6.170s
   sys     0m0.305s
  ```
