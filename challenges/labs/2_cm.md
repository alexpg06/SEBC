# Repos in Second Node
<pre class="prettyprint">
[root@ip-10-1-2-155 centos]# ls /etc/yum.repos.d
CentOS-Base.repo  CentOS-CR.repo  CentOS-Debuginfo.repo  CentOS-fasttrack.repo  CentOS-Media.repo  CentOS-Sources.repo  CentOS-Vault.repo  cloudera-manager.repo
</pre>


# Installing Cloudera Manager 5.11
<pre class="prettyprint">
[root@ip-10-1-2-155 centos]# yum install cloudera-manager-daemons cloudera-manager-server
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.cs.pitt.edu
 * extras: mirror.vtti.vt.edu
 * updates: mirror.es.its.nyu.edu
Resolving Dependencies
--> Running transaction check
---> Package cloudera-manager-daemons.x86_64 0:5.11.2-1.cm5112.p0.6.el7 will be installed
---> Package cloudera-manager-server.x86_64 0:5.11.2-1.cm5112.p0.6.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===========================================================================================================================================================================================================================
 Package                                                    Arch                                     Version                                                      Repository                                          Size
===========================================================================================================================================================================================================================
Installing:
 cloudera-manager-daemons                                   x86_64                                   5.11.2-1.cm5112.p0.6.el7                                     cloudera-manager                                   651 M
 cloudera-manager-server                                    x86_64                                   5.11.2-1.cm5112.p0.6.el7                                     cloudera-manager                                   8.5 k

Transaction Summary
===========================================================================================================================================================================================================================
Install  2 Packages

Total download size: 651 M
Installed size: 826 M
Is this ok [y/d/N]: y
Downloading packages:
(1/2): cloudera-manager-server-5.11.2-1.cm5112.p0.6.el7.x86_64.rpm                                                                                                                                  | 8.5 kB  00:00:00     
(2/2): cloudera-manager-daemons-5.11.2-1.cm5112.p0.6.el7.x86_64.rpm                                                                                                                                 | 651 MB  00:00:14     
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                                       46 MB/s | 651 MB  00:00:14     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : cloudera-manager-daemons-5.11.2-1.cm5112.p0.6.el7.x86_64                                                                                                                                                1/2 
  Installing : cloudera-manager-server-5.11.2-1.cm5112.p0.6.el7.x86_64                                                                                                                                                 2/2 
  Verifying  : cloudera-manager-server-5.11.2-1.cm5112.p0.6.el7.x86_64                                                                                                                                                 1/2 
  Verifying  : cloudera-manager-daemons-5.11.2-1.cm5112.p0.6.el7.x86_64                                                                                                                                                2/2 

Installed:
  cloudera-manager-daemons.x86_64 0:5.11.2-1.cm5112.p0.6.el7                                                   cloudera-manager-server.x86_64 0:5.11.2-1.cm5112.p0.6.el7                                                  

Complete!
[root@ip-10-1-2-155 centos]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-10-1-2-173.ec2.internal mysql scm node2 mariaSEBC
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
[root@ip-10-1-2-155 centos]# service cloudera-scm-server start
Starting cloudera-scm-server (via systemctl):              [  OK  ]
[root@ip-10-1-2-155 centos]# service cloudera-scm-server status
/etc/init.d/cloudera-scm-server: line 109: pstree: command not found
● cloudera-scm-server.service - LSB: Cloudera SCM Server
   Loaded: loaded (/etc/rc.d/init.d/cloudera-scm-server; bad; vendor preset: disabled)
   Active: active (exited) since Fri 2017-12-01 11:14:00 CST; 4s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 7025 ExecStart=/etc/rc.d/init.d/cloudera-scm-server start (code=exited, status=0/SUCCESS)

Dec 01 11:13:55 ip-10-1-2-155.ec2.internal systemd[1]: Starting LSB: Cloudera SCM Server...
Dec 01 11:13:55 ip-10-1-2-155.ec2.internal cloudera-scm-server[7025]: /etc/rc.d/init.d/cloudera-scm-server: line 109: pstree: command not found
Dec 01 11:13:55 ip-10-1-2-155.ec2.internal su[7049]: (to cloudera-scm) root on none
Dec 01 11:14:00 ip-10-1-2-155.ec2.internal cloudera-scm-server[7025]: Starting cloudera-scm-server: [  OK  ]
Dec 01 11:14:00 ip-10-1-2-155.ec2.internal systemd[1]: Started LSB: Cloudera SCM Server.
</pre>
