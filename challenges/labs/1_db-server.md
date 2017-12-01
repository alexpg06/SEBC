

# Hostname
<pre class="prettyprint">
[root@ip-10-1-2-173 centos]# hostname
ip-10-1-2-173.ec2.internal
</pre>

# MySQL Version
<pre class="prettyprint">
[root@ip-10-1-2-173 centos]# mysql -V
mysql  Ver 15.1 Distrib 5.5.56-MariaDB, for Linux (x86_64) using readline 5.1
</pre>

# Databases List
<pre class="prettyprint">
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| test               |
+--------------------+
9 rows in set (0.00 sec)
</pre>

