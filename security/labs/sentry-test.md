#Sentry Test Lab

```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG: Mladen-Trampic-SRB-1989
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019115555_b47e15b4-327d-4733-b9cb-b3729dc45e45): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019115555_b47e15b4-327d-4733-b9cb-b3729dc45e45); Time taken: 0.818 seconds
INFO  : Executing command(queryId=hive_20171019115555_b47e15b4-327d-4733-b9cb-b3729dc45e45): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019115555_b47e15b4-327d-4733-b9cb-b3729dc45e45); Time taken: 0.468 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.7 seconds)
0: jdbc:hive2://localhost:10000/default>
```

# Work in progress

```
[root@ip-172-31-33-245 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG: Mladen-Trampic-SRB-1989
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER `ip-172-31-33-245.eu-central-1.compute.internal` TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171019122222_89037909-b5be-407a-8f12-59dcc3874b23): GRANT ALL ON SERVER `ip-172-31-33-245.eu-central-1.compute.internal` TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171019122222_89037909-b5be-407a-8f12-59dcc3874b23); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20171019122222_89037909-b5be-407a-8f12-59dcc3874b23): GRANT ALL ON SERVER `ip-172-31-33-245.eu-central-1.compute.internal` TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019122222_89037909-b5be-407a-8f12-59dcc3874b23); Time taken: 0.043 seconds
INFO  : OK
No rows affected (0.165 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP `Mladen-Trampic-SRB-1989`;
INFO  : Compiling command(queryId=hive_20171019122222_0c09cd31-118c-416f-89a2-8eff96651339): GRANT ROLE sentry_admin TO GROUP `Mladen-Trampic-SRB-1989`
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171019122222_0c09cd31-118c-416f-89a2-8eff96651339); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171019122222_0c09cd31-118c-416f-89a2-8eff96651339): GRANT ROLE sentry_admin TO GROUP `Mladen-Trampic-SRB-1989`
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019122222_0c09cd31-118c-416f-89a2-8eff96651339); Time taken: 0.022 seconds
INFO  : OK
No rows affected (0.086 seconds)
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019122222_06f2e055-2bf4-43ff-b643-8f4ac4d33ed8): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019122222_06f2e055-2bf4-43ff-b643-8f4ac4d33ed8); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171019122222_06f2e055-2bf4-43ff-b643-8f4ac4d33ed8): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019122222_06f2e055-2bf4-43ff-b643-8f4ac4d33ed8); Time taken: 0.135 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.257 seconds)
0: jdbc:hive2://localhost:10000/default>
```


# As George
```
[root@ip-172-31-33-245 ~]# kinit george
Password for george@MLADEN-TRAMPIC-SRB-1989.SG:
[root@ip-172-31-33-245 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> GRANT ROLE reads TO GROUP selector;[root@ip-172-31-33-245 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG: george
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG:
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019123131_c1fa2fa5-773d-4f4a-b8b6-d31460f1429c): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019123131_c1fa2fa5-773d-4f4a-b8b6-d31460f1429c); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20171019123131_c1fa2fa5-773d-4f4a-b8b6-d31460f1429c): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019123131_c1fa2fa5-773d-4f4a-b8b6-d31460f1429c); Time taken: 0.125 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.327 seconds)
0: jdbc:hive2://localhost:10000/default>
```

# As Ferdinand
```
[root@ip-172-31-33-245 ~]# kinit ferdinand
Password for ferdinand@MLADEN-TRAMPIC-SRB-1989.SG:
[root@ip-172-31-33-245 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG: ferdinand
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-33-245.eu-central-1.compute.internal@MLADEN-TRAMPIC-SRB-1989.SG:
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019123232_e4186e12-316a-47ea-bed4-7f2f0fdd0b85): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019123232_e4186e12-316a-47ea-bed4-7f2f0fdd0b85); Time taken: 0.079 seconds
INFO  : Executing command(queryId=hive_20171019123232_e4186e12-316a-47ea-bed4-7f2f0fdd0b85): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019123232_e4186e12-316a-47ea-bed4-7f2f0fdd0b85); Time taken: 0.155 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.389 seconds)
0: jdbc:hive2://localhost:10000/default>

```
