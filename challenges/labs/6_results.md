*  Login to beeline with the principal for ernest
```
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171020103131_0394db9c-4bdd-40bb-90f5-6e21b686216c): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171020103131_0394db9c-4bdd-40bb-90f5-6e21b686216c); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20171020103131_0394db9c-4bdd-40bb-90f5-6e21b686216c): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171020103131_0394db9c-4bdd-40bb-90f5-6e21b686216c); Time taken: 0.111 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.289 seconds)
```