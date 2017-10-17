## <center> HDFS Lab: Replicate to another cluster

Node: Data replication in the cloud depends on peers that can see each
other's nodes.

* Choose a partner in class
* Name a source directory after your GitHub handle
* Name a target directory after your partner's GitHub handle
* Use `teragen` to create a 500 MB file
* Copy your partner's file to your target directory 
    * Let one partner use `distCp` on the command line
    * Let the other use BDR
* Browse the results 
    * Use `hdfs fsck <path> -files -blocks` on your source and target directories
    * Copy the work for this lab into `storage/labs/0_replication.md`

---