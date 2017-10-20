# Put the following in the file `challenges/labs/1_mysql.md`
* The hostname of your MySQL node 
```
Private_Hostname: ip-172-31-34-39.eu-west-1.compute.internal
```
  * aka 
  ```
   Node: 1
   Public_Hostname: ec2-54-229-56-204.eu-west-1.compute.amazonaws.com
   Public_IP: 54.229.56.204
   Private_Hostname: ip-172-31-34-39.eu-west-1.compute.internal
   Private_IP: 172.31.34.39
  ```
* The command and output for `mysql --version`
```
[root@ip-172-31-34-39 ~]# mysql --version
mysql  Ver 14.14 Distrib 5.5.58, for Linux (x86_64) using readline 5.1
```
* The command and output for listing MySQL databases 
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)

```