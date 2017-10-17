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
    * Let one partner use `distCp` on the command line
    * Let the other use BDR
* Browse the results 
    * Use `hdfs fsck <path> -files -blocks` on your source and target directories
    * Copy the work for this lab into `storage/labs/0_replication.md`

