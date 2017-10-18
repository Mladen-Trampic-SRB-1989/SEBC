## <center> HDFS Lab: Replicate to another cluster

Node: Data replication in the cloud depends on peers that can see each
other's nodes.

* Choose a partner in class
    * github handle feanor21 [https://github.com/feanor21](url)
   
* Name a source directory after your GitHub handle
```
HADOOP_USER_NAME=hdfs hdfs dfs -mkdir /user/Mladen-Trampic-SRB-1989
```
	
* Name a target directory after your partner's GitHub handle
```
HADOOP_USER_NAME=hdfs hdfs dfs -mkdir /user/Mladen-Trampic-SRB-1989
```
	
* Use `teragen` to create a 500 MB file
```
HADOOP_USER_NAME=hdfs hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-mapreduce-examples-2.6.0-cdh5.8.3.jar \
teragen 5242880 /user/Mladen-Trampic-SRB-1989/teragen-input
```

* Copy your partner's file to your target directory 
	
(Within issues i posted explanation why i can not distcp, due AWS Regions, using distcp inside cluster itself using hftp protocol towards hdfs protocol )

See issue [#3](/../../issues/3)

```
HADOOP_USER_NAME=hdfs hadoop distcp hftp://`hostname`:50070/user/Mladen-Trampic-SRB-1989/teragen-input hdfs://`hostname`:8020/user/feanor21
```

* Browse the results
```
HADOOP_USER_NAME=hdfs hdfs dfs -ls /user/feanor21
```

* Use `hdfs fsck <path> -files -blocks` on your source and target directories
     * Source directory:
     ```
      [centos@ip-172-31-33-245 ~]$ HADOOP_USER_NAME=hdfs hdfs fsck /user/Mladen-Trampic-SRB-1989/teragen-input -files -blocks
      Connecting to namenode via http://ip-172-31-33-245.eu-central-1.compute.internal:50070
      FSCK started by hdfs (auth:SIMPLE) from /172.31.33.245 for path /user/Mladen-Trampic-SRB-1989/teragen-input at Tue Oct 17 11:17:36 UTC 2017
      /user/Mladen-Trampic-SRB-1989/teragen-input <dir>
      /user/Mladen-Trampic-SRB-1989/teragen-input/_SUCCESS 0 bytes, 0 block(s):  OK
      
      /user/Mladen-Trampic-SRB-1989/teragen-input/part-m-00000 262144000 bytes, 2 block(s):  OK
      0. BP-1763593649-172.31.33.245-1508186930425:blk_1073744037_3213 len=134217728 Live_repl=3
      1. BP-1763593649-172.31.33.245-1508186930425:blk_1073744040_3216 len=127926272 Live_repl=3
      
      /user/Mladen-Trampic-SRB-1989/teragen-input/part-m-00001 262144000 bytes, 2 block(s):  OK
      0. BP-1763593649-172.31.33.245-1508186930425:blk_1073744036_3212 len=134217728 Live_repl=3
      1. BP-1763593649-172.31.33.245-1508186930425:blk_1073744039_3215 len=127926272 Live_repl=3
      
      Status: HEALTHY
       Total size:    524288000 B
       Total dirs:    1
       Total files:   3
       Total symlinks:                0
       Total blocks (validated):      4 (avg. block size 131072000 B)
       Minimally replicated blocks:   4 (100.0 %)
       Over-replicated blocks:        0 (0.0 %)
       Under-replicated blocks:       0 (0.0 %)
       Mis-replicated blocks:         0 (0.0 %)
       Default replication factor:    3
       Average block replication:     3.0
       Corrupt blocks:                0
       Missing replicas:              0 (0.0 %)
       Number of data-nodes:          4
       Number of racks:               1
      FSCK ended at Tue Oct 17 11:17:36 UTC 2017 in 2 milliseconds
      
      
      The filesystem under path '/user/Mladen-Trampic-SRB-1989/teragen-input' is HEALTHY
     ```

     * Target directory
	 
     ```
      [centos@ip-172-31-33-245 ~]$ HADOOP_USER_NAME=hdfs hdfs fsck /user/feanor21/teragen-input -files -blocks
      Connecting to namenode via http://ip-172-31-33-245.eu-central-1.compute.internal:50070
      FSCK started by hdfs (auth:SIMPLE) from /172.31.33.245 for path /user/feanor21/teragen-input at Tue Oct 17 11:19:11 UTC 2017
      /user/feanor21/teragen-input <dir>
      /user/feanor21/teragen-input/_SUCCESS 0 bytes, 0 block(s):  OK
      
      /user/feanor21/teragen-input/part-m-00000 262144000 bytes, 2 block(s):  OK
      0. BP-1763593649-172.31.33.245-1508186930425:blk_1073744063_3239 len=134217728 Live_repl=3
      1. BP-1763593649-172.31.33.245-1508186930425:blk_1073744066_3242 len=127926272 Live_repl=3
      
      /user/feanor21/teragen-input/part-m-00001 262144000 bytes, 2 block(s):  OK
      0. BP-1763593649-172.31.33.245-1508186930425:blk_1073744065_3241 len=134217728 Live_repl=3
      1. BP-1763593649-172.31.33.245-1508186930425:blk_1073744067_3243 len=127926272 Live_repl=3
      
      Status: HEALTHY
       Total size:    524288000 B
       Total dirs:    1
       Total files:   3
       Total symlinks:                0
       Total blocks (validated):      4 (avg. block size 131072000 B)
       Minimally replicated blocks:   4 (100.0 %)
       Over-replicated blocks:        0 (0.0 %)
       Under-replicated blocks:       0 (0.0 %)
       Mis-replicated blocks:         0 (0.0 %)
       Default replication factor:    3
       Average block replication:     3.0
       Corrupt blocks:                0
       Missing replicas:              0 (0.0 %)
       Number of data-nodes:          4
       Number of racks:               1
      FSCK ended at Tue Oct 17 11:19:11 UTC 2017 in 2 milliseconds
      
      
      The filesystem under path '/user/feanor21/teragen-input' is HEALTHY
     ```


