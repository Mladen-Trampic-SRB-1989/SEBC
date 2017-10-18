# Upgrade Cloudera Manager

  * Backup on CM node db.properties file
  ```
   [root@ip-172-31-33-245 ~]# cp /etc/cloudera-scm-server/db.properties ~/
  ```
  * Backup scm CM's MariaDB database:
  ```
   mysqldump -uscm -p scm > scm_dump.sql
  ```
  * Stop cloudera-scm-server.service, cloduera-scm-agent service
    * Stop Agents on other nodes
  ```
   systemctl stop cloudera-scm-server
   systemctl stop cloudera-scm-agent
  ```
  * Modify /etc/yum.repos.d/cloudera-manager.repo , replace basename url 
  ```
   [cloudera-manager]
   # Packages for Cloudera Manager, Version 5, on RedHat or CentOS 7 x86_64
   name=Cloudera Manager
   #baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.8.3/
   baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.9/
   gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
   gpgcheck = 1
  ```
  * Start update process of CM Server, Agents
  ```
   yum --disablerepo=* --enablerepo=cloudera-manager update -y
  ```
  * Start Cloudera Manager Server, Agents
  ```
   systemctl start cloudera-scm-server
   systemctl start cloudera-scm-agent
  ```
  * Tail log, wait for CM server to start up:
  ```
   tail -n2000 -f /var/log/cloudera-scm-server/cloudera-scm-server.log
  ```
    * eg..
    ```
     2017-10-18 10:06:20,938 INFO WebServerImpl:org.mortbay.log: Started SelectChannelConnector@0.0.0.0:7180
    ```
  * Restart cluster services.