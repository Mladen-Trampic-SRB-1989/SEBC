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
   