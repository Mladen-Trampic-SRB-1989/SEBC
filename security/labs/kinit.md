# Security kinit.md file
  * The kinit command you use to authenticate your test use ( In my use-case my github handle Mladen-Trampic-SRB-1989 )
    * my default realm is setted to be : MLADEN-TRAMPIC-SRB-1989.SG, therefore command was quite simple:
    ```
     [root@ip-172-31-33-245 ~]# kinit Mladen-Trampic-SRB-1989
      Password for Mladen-Trampic-SRB-1989@MLADEN-TRAMPIC-SRB-1989.SG:
	```
	* The output from a klist command listing your credentials and ticket lifetime:
	```
	 [root@ip-172-31-33-245 ~]# klist
     Ticket cache: FILE:/tmp/krb5cc_0
     Default principal: Mladen-Trampic-SRB-1989@MLADEN-TRAMPIC-SRB-1989.SG
     
     Valid starting       Expires              Service principal
     10/19/2017 11:08:39  10/20/2017 11:08:39  krbtgt/MLADEN-TRAMPIC-SRB-1989.SG@MLADEN-TRAMPIC-SRB-1989.SG
             renew until 10/26/2017 11:08:39
	```