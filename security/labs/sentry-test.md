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
