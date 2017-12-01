####################### TEST USER #########################

[centos@ip-10-1-2-181 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1000
Default principal: centos@ALEXSEBC.COM

Valid starting       Expires              Service principal
11/29/2017 14:28:49  11/30/2017 14:28:49  krbtgt/ALEXSEBC.COM@ALEXSEBC.COM
	renew until 12/06/2017 14:28:49
[centos@ip-10-1-2-181 ~]$ beeline -u 'jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/_HOST@ALEXSEBC.COM'
scan complete in 1ms
Connecting to jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/_HOST@ALEXSEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> show tables;
INFO  : Compiling command(queryId=hive_20171129144040_e7c40459-9af9-467b-a0a5-793099292f58): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129144040_e7c40459-9af9-467b-a0a5-793099292f58); Time taken: 0.701 seconds
INFO  : Executing command(queryId=hive_20171129144040_e7c40459-9af9-467b-a0a5-793099292f58): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129144040_e7c40459-9af9-467b-a0a5-793099292f58); Time taken: 0.464 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.505 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> 

#################### GEORGE ####################

[george@ip-10-1-2-181 ~]$ kinit
Password for george@ALEXSEBC.COM: 
[george@ip-10-1-2-181 ~]$ beeline -u 'jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/_HOST@ALEXSEBC.COM'
scan complete in 2ms
Connecting to jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/_HOST@ALEXSEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129150000_d367c414-e393-4e06-adb1-668361f6b0a1): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129150000_d367c414-e393-4e06-adb1-668361f6b0a1); Time taken: 0.073 seconds
INFO  : Executing command(queryId=hive_20171129150000_d367c414-e393-4e06-adb1-668361f6b0a1): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129150000_d367c414-e393-4e06-adb1-668361f6b0a1); Time taken: 0.145 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.316 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10>

####################### FERDINAND #########################

[ferdinand@ip-10-1-2-181 ~]$ kinit
Password for ferdinand@ALEXSEBC.COM: 
[ferdinand@ip-10-1-2-181 ~]$ beeline -u 'jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/_HOST@ALEXSEBC.COM'
scan complete in 2ms
Connecting to jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/_HOST@ALEXSEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129150202_ef866b2b-5b49-49d2-9a2f-2f7db38e4574): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129150202_ef866b2b-5b49-49d2-9a2f-2f7db38e4574); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20171129150202_ef866b2b-5b49-49d2-9a2f-2f7db38e4574): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129150202_ef866b2b-5b49-49d2-9a2f-2f7db38e4574); Time taken: 0.144 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.321 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> 