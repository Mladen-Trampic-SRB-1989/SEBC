*  List the command and output of ls /etc/yum.repos.d in challenges/labs/2_cm.md

```
[root@ip-172-31-38-249 ~]# ls -l /etc/yum.repos.d/
total 36
-rw-r--r--. 1 root root 1664 Dec  9  2015 CentOS-Base.repo
-rw-r--r--. 1 root root 1309 Dec  9  2015 CentOS-CR.repo
-rw-r--r--. 1 root root  649 Dec  9  2015 CentOS-Debuginfo.repo
-rw-r--r--. 1 root root  290 Dec  9  2015 CentOS-fasttrack.repo
-rw-r--r--. 1 root root  630 Dec  9  2015 CentOS-Media.repo
-rw-r--r--. 1 root root 1331 Dec  9  2015 CentOS-Sources.repo
-rw-r--r--. 1 root root 1952 Dec  9  2015 CentOS-Vault.repo
-rw-r--r--  1 root root  356 Oct 20 08:36 cloudera-manager.repo
-rw-r--r--  1 root root 1885 Oct 20 08:09 mysql-community.repo
```

* Use the scm_prepare_database.sh script to write your db.properties file
```
[root@ip-172-31-38-249 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm_pwd -h ip-172-31-34-39.eu-west-1.compute.internal
JAVA_HOME=/usr/java/jdk1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[main] DbCommandExecutor INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```