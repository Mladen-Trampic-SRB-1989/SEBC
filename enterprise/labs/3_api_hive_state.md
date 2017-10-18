* Write curl statements that stop, start, and check the current state of your Hive service.
  * Command to stop : 
  ```
   curl -X POST -u "username:password" -i http://ec2-54-93-198-167.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/cluster/services/hive/commands/stop
  ```
  * Command to start :
  ```
   curl -X POST -u "username:password" -i http://ec2-54-93-198-167.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/cluster/services/hive/commands/start
  ```
  * Command to get current state of Hive service:
  ```
   curl -X POST -u "username:password" -i http://ec2-54-93-198-167.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/cluster/services/hive
  ```
    * Alternatevly only service state, we can grep :
	```
	 curl -X POST -u "username:password" -i http://ec2-54-93-198-167.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/cluster/services/hive | grep serviceState
	```