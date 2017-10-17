* Create a precious directory in HDFS; copy the ZIP course file into it.
```
 HADOOP_USER_NAME=hdfs hdfs dfs -mkdir /precious
 HADOOP_USER_NAME=hdfs hdfs dfs -put $PATH_TO_FILE/SEBC-master.zip /precious
```

* Enable snapshots for precious
  * In my exercise i did with Cloudera Manager, but same effect using shell:
  ```
   HADOOP_USER_NAME=hdfs hdfs dfsadmin -allowSnapshot /precious
  ```

* Create a snapshot called sebc-hdfs-test
```
 HADOOP_USER_NAME=hdfs hdfs dfs -createSnapshot /precious sebc-hdfs-test
```

* Delete the directory
```
 HADOOP_USER_NAME=hdfs hdfs dfs -rm -r -f -skipTrash /precious
```
  * Command failed with reasons:
  ```
   rm: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
  ```

* Delete the ZIP file
```
 HADOOP_USER_NAME=hdfs hdfs dfs -rm -r -f -skipTrash /precious/SEBC-master.zip
```

* Restore the deleted file
  * Did it with Cloudera Manager, but same effect can be done with following (using hdfs dfs cp, or hadoop distcp):
  ```
   [root@ip-172-31-42-124 ~]# HADOOP_USER_NAME=hdfs hdfs dfs -ls -R /precious/.snapshot
   drwxr-xr-x   - hdfs supergroup          0 2017-10-17 12:27 /precious/.snapshot/sebc-hdfs-test
   -rw-r--r--   3 hdfs supergroup     948434 2017-10-17 12:23 /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip
   
   [root@ip-172-31-42-124 ~]# HADOOP_USER_NAME=hdfs hdfs dfs -cp /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /precious/
  ```
