* Command and output for hdfs dfs -ls /user
```
[root@ip-172-31-34-39 ~]# HADOOP_USER_NAME=hdfs hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - ernest  hadoop          0 2017-10-20 09:17 /user/ernest
drwxrwxrwx   - mapred  hadoop          0 2017-10-20 09:13 /user/history
drwxrwxr-t   - hive    hive            0 2017-10-20 09:14 /user/hive
drwxrwxr-x   - hue     hue             0 2017-10-20 09:15 /user/hue
drwxrwxr-x   - oozie   oozie           0 2017-10-20 09:15 /user/oozie
drwxr-xr-x   - siwicki hadoop          0 2017-10-20 09:17 /user/siwicki
```
You don't need to assume `hdfs` privileges to list directories. 
```
* The output from the CM API call ../api/v14/hosts
  * Command:
  ```
  curl -X GET -u "admin:admin" http://ec2-54-171-75-58.eu-west-1.compute.amazonaws.com:7180/api/v14/hosts
  ```
  * Output:
  ```
  {
  "items" : [ {
      "hostId" : "ae09e4b4-aec3-44b5-9b9a-12ae2806f44d",
      "ipAddress" : "172.31.34.39",
      "hostname" : "ip-172-31-34-39.eu-west-1.compute.internal",
      "rackId" : "/default",
      "hostUrl" : "http://ip-172-31-38-249.eu-west-1.compute.internal:7180/cmf/hostRedirect/ae09e4b4-aec3-44b5-9b9a-12ae2806f44d",
      "maintenanceMode" : false,
      "maintenanceOwners" : [ ],
      "commissionState" : "COMMISSIONED",
      "numCores" : 4,
      "numPhysicalCores" : 2,
      "totalPhysMemBytes" : 15332438016
    }, {
      "hostId" : "8218e2a2-6b96-42e0-8975-7b2040969a76",
      "ipAddress" : "172.31.38.249",
      "hostname" : "ip-172-31-38-249.eu-west-1.compute.internal",
      "rackId" : "/default",
      "hostUrl" : "http://ip-172-31-38-249.eu-west-1.compute.internal:7180/cmf/hostRedirect/8218e2a2-6b96-42e0-8975-7b2040969a76",
      "maintenanceMode" : false,
      "maintenanceOwners" : [ ],
      "commissionState" : "COMMISSIONED",
      "numCores" : 4,
      "numPhysicalCores" : 2,
      "totalPhysMemBytes" : 15332438016
    }, {
      "hostId" : "bdfb8be7-b441-41a4-a420-a7208fcdf579",
      "ipAddress" : "172.31.40.178",
      "hostname" : "ip-172-31-40-178.eu-west-1.compute.internal",
      "rackId" : "/default",
      "hostUrl" : "http://ip-172-31-38-249.eu-west-1.compute.internal:7180/cmf/hostRedirect/bdfb8be7-b441-41a4-a420-a7208fcdf579",
      "maintenanceMode" : false,
      "maintenanceOwners" : [ ],
      "commissionState" : "COMMISSIONED",
      "numCores" : 4,
      "numPhysicalCores" : 2,
      "totalPhysMemBytes" : 15332438016
    }, {
      "hostId" : "085744b6-a280-4587-a678-0ccd5c246c87",
      "ipAddress" : "172.31.41.191",
      "hostname" : "ip-172-31-41-191.eu-west-1.compute.internal",
      "rackId" : "/default",
      "hostUrl" : "http://ip-172-31-38-249.eu-west-1.compute.internal:7180/cmf/hostRedirect/085744b6-a280-4587-a678-0ccd5c246c87",
      "maintenanceMode" : false,
      "maintenanceOwners" : [ ],
      "commissionState" : "COMMISSIONED",
      "numCores" : 4,
      "numPhysicalCores" : 2,
      "totalPhysMemBytes" : 15332438016
    }, {
      "hostId" : "1fc37ed7-ebdd-4e59-b5f7-11bd8e7552a9",
      "ipAddress" : "172.31.43.139",
      "hostname" : "ip-172-31-43-139.eu-west-1.compute.internal",
      "rackId" : "/default",
      "hostUrl" : "http://ip-172-31-38-249.eu-west-1.compute.internal:7180/cmf/hostRedirect/1fc37ed7-ebdd-4e59-b5f7-11bd8e7552a9",
      "maintenanceMode" : false,
      "maintenanceOwners" : [ ],
      "commissionState" : "COMMISSIONED",
      "numCores" : 4,
      "numPhysicalCores" : 2,
      "totalPhysMemBytes" : 15332438016
    } ]
  }
  ```
