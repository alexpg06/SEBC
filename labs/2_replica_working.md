---
<div style="page-break-after: always;"></div>

# <center>CM Install Lab 
## <center> Maria DB with replication

<strong>Install MariaDB</strong>
<pre class="prettyprint">
[root@ip-10-1-2-143 centos]# mysql -u root -p
Enter password: 
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 5
Server version: 5.5.56-MariaDB MariaDB Server

Copyright (c) 2000, 2017, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> STOP SLAVE;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> CHANGE MASTER TO
    ->   MASTER_HOST='ec2-52-207-231-115.compute-1.amazonaws.com.',
    ->   MASTER_USER='replication_user',
    ->   MASTER_PORT=3306,
    ->   MASTER_CONNECT_RETRY=10;
Query OK, 0 rows affected (0.01 sec)

MariaDB [(none)]> START SLAVE;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> show slave status;
+----------------------------------+---------------------------------------------+------------------+-------------+---------------+-----------------+---------------------+-----------------------+---------------+-----------------------+------------------+-------------------+-----------------+---------------------+--------------------+------------------------+-------------------------+-----------------------------+------------+------------+--------------+---------------------+-----------------+-----------------+----------------+---------------+--------------------+--------------------+--------------------+-----------------+-------------------+----------------+-----------------------+-------------------------------+---------------+---------------+----------------+----------------+-----------------------------+------------------+
| Slave_IO_State                   | Master_Host                                 | Master_User      | Master_Port | Connect_Retry | Master_Log_File | Read_Master_Log_Pos | Relay_Log_File        | Relay_Log_Pos | Relay_Master_Log_File | Slave_IO_Running | Slave_SQL_Running | Replicate_Do_DB | Replicate_Ignore_DB | Replicate_Do_Table | Replicate_Ignore_Table | Replicate_Wild_Do_Table | Replicate_Wild_Ignore_Table | Last_Errno | Last_Error | Skip_Counter | Exec_Master_Log_Pos | Relay_Log_Space | Until_Condition | Until_Log_File | Until_Log_Pos | Master_SSL_Allowed | Master_SSL_CA_File | Master_SSL_CA_Path | Master_SSL_Cert | Master_SSL_Cipher | Master_SSL_Key | Seconds_Behind_Master | Master_SSL_Verify_Server_Cert | Last_IO_Errno | Last_IO_Error | Last_SQL_Errno | Last_SQL_Error | Replicate_Ignore_Server_Ids | Master_Server_Id |
+----------------------------------+---------------------------------------------+------------------+-------------+---------------+-----------------+---------------------+-----------------------+---------------+-----------------------+------------------+-------------------+-----------------+---------------------+--------------------+------------------------+-------------------------+-----------------------------+------------+------------+--------------+---------------------+-----------------+-----------------+----------------+---------------+--------------------+--------------------+--------------------+-----------------+-------------------+----------------+-----------------------+-------------------------------+---------------+---------------+----------------+----------------+-----------------------------+------------------+
| Waiting for master to send event | ec2-52-207-231-115.compute-1.amazonaws.com. | replication_user |        3306 |            10 | sebc-bin.000001 |                 370 | sebc-relay-bin.000002 |           653 | sebc-bin.000001       | Yes              | Yes               |                 |                     |                    |                        |                         |                             |          0 |            |            0 |                 370 |             946 | None            |                |             0 | No                 |                    |                    |                 |                   |                |                     0 | No                            |             0 |               |              0 |                |                             |                1 |
+----------------------------------+---------------------------------------------+------------------+-------------+---------------+-----------------+---------------------+-----------------------+---------------+-----------------------+------------------+-------------------+-----------------+---------------------+--------------------+------------------------+-------------------------+-----------------------------+------------+------------+--------------+---------------------+-----------------+-----------------+----------------+---------------+--------------------+--------------------+--------------------+-----------------+-------------------+----------------+-----------------------+-------------------------------+---------------+---------------+----------------+----------------+-----------------------------+------------------+
1 row in set (0.00 sec)

MariaDB [(none)]> exit;
Bye
</pre>
