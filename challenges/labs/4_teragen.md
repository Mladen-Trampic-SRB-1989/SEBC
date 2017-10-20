* Full teragen command:
```
time hadoop jar \
 /opt/cloudera/parcels/CDH/jars/hadoop-mapreduce-examples-2.6.0-cdh5*.jar \
 teragen \
 -D dfs.block.size=33554432 \
 -D mapreduce.job.maps=6 \
 51200000 \
 tgen512m | tee outputOfJob.log
```

* The output of the time command
```
17/10/20 09:29:09 INFO mapreduce.Job: Job job_1508490826182_0001 completed successfully
17/10/20 09:29:10 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=741690
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=511
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=24
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=6
                Other local map tasks=6
                Total time spent by all maps in occupied slots (ms)=194980
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=194980
                Total vcore-seconds taken by all map tasks=194980
                Total megabyte-seconds taken by all map tasks=199659520
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Input split bytes=511
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1283
                CPU time spent (ms)=100210
                Physical memory (bytes) snapshot=2299584512
                Virtual memory (bytes) snapshot=16728231936
                Total committed heap usage (bytes)=2189426688
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=109963291816450258
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=5120000000

real    0m47.955s
user    0m6.816s
sys     0m0.296s

```

* The command and output of hdfs dfs -ls /user/ernest/tgen512m
```
[ernest@ip-172-31-34-39 ~]$ hdfs dfs -ls /user/ernest/tgen512m
Found 7 items
-rw-r--r--   3 ernest hadoop          0 2017-10-20 09:29 /user/ernest/tgen512m/_SUCCESS
-rw-r--r--   3 ernest hadoop  853333400 2017-10-20 09:29 /user/ernest/tgen512m/part-m-00000
-rw-r--r--   3 ernest hadoop  853333300 2017-10-20 09:29 /user/ernest/tgen512m/part-m-00001
-rw-r--r--   3 ernest hadoop  853333300 2017-10-20 09:29 /user/ernest/tgen512m/part-m-00002
-rw-r--r--   3 ernest hadoop  853333400 2017-10-20 09:29 /user/ernest/tgen512m/part-m-00003
-rw-r--r--   3 ernest hadoop  853333300 2017-10-20 09:29 /user/ernest/tgen512m/part-m-00004
-rw-r--r--   3 ernest hadoop  853333300 2017-10-20 09:29 /user/ernest/tgen512m/part-m-00005
```