# Repos in Second Node
<pre class="prettyprint">
[root@ip-10-1-2-155 centos]# ls /etc/yum.repos.d
CentOS-Base.repo  CentOS-CR.repo  CentOS-Debuginfo.repo  CentOS-fasttrack.repo  CentOS-Media.repo  CentOS-Sources.repo  CentOS-Vault.repo  cloudera-manager.repo
</pre>


# Connect Cloudera Manager Server to its database
<pre class="prettyprint">
[root@ip-10-1-2-155 centos]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-10-1-2-173.ec2.internal mysql scm node2 mariaSEBC
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
</pre>
