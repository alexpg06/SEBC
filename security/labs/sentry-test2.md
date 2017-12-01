[alexpg06@ip-10-1-2-181 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: alexpg06@ALEXSEBC.COM

Valid starting       Expires              Service principal
11/29/2017 12:49:03  11/30/2017 12:49:03  krbtgt/ALEXSEBC.COM@ALEXSEBC.COM
	renew until 12/06/2017 12:49:03
[alexpg06@ip-10-1-2-181 ~]$ beeline -u 'jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/ip-10-1-2-143.ec2.internal@ALEXSEBC.COM'
scan complete in 1ms
Connecting to jdbc:hive2://ip-10-1-2-143.ec2.internal:10000/default;principal=hive/ip-10-1-2-143.ec2.internal@ALEXSEBC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171129144343_140d337a-076c-4b85-90e3-75139c09f5b5): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129144343_140d337a-076c-4b85-90e3-75139c09f5b5); Time taken: 0.093 seconds
INFO  : Executing command(queryId=hive_20171129144343_140d337a-076c-4b85-90e3-75139c09f5b5): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129144343_140d337a-076c-4b85-90e3-75139c09f5b5); Time taken: 0.53 seconds
INFO  : OK
No rows affected (0.681 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171129144343_6d58a127-7ba9-4a49-853b-1cd6745dcb4b): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129144343_6d58a127-7ba9-4a49-853b-1cd6745dcb4b); Time taken: 0.084 seconds
INFO  : Executing command(queryId=hive_20171129144343_6d58a127-7ba9-4a49-853b-1cd6745dcb4b): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129144343_6d58a127-7ba9-4a49-853b-1cd6745dcb4b); Time taken: 0.09 seconds
INFO  : OK
No rows affected (0.188 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> GRANT ROLE sentry_admin TO GROUP alexpg06;
INFO  : Compiling command(queryId=hive_20171129144343_b8c236c9-2c87-4c82-b5c2-118da56d94cd): GRANT ROLE sentry_admin TO GROUP alexpg06
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129144343_b8c236c9-2c87-4c82-b5c2-118da56d94cd); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171129144343_b8c236c9-2c87-4c82-b5c2-118da56d94cd): GRANT ROLE sentry_admin TO GROUP alexpg06
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129144343_b8c236c9-2c87-4c82-b5c2-118da56d94cd); Time taken: 0.076 seconds
INFO  : OK
No rows affected (0.157 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129144343_bdcbc172-824b-4aef-aec4-d30d2554a433): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129144343_bdcbc172-824b-4aef-aec4-d30d2554a433); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20171129144343_bdcbc172-824b-4aef-aec4-d30d2554a433): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129144343_bdcbc172-824b-4aef-aec4-d30d2554a433); Time taken: 0.239 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.4 seconds)
0: jdbc:hive2://ip-10-1-2-143.ec2.internal:10> 