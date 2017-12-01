


# Repo configuration
<pre class="prettyprint">
[root@ip-10-1-2-173 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.cs.pitt.edu
 * extras: mirror.linux.duke.edu
 * updates: mirror.es.its.nyu.edu
repo id                                                                 repo name                                                                  status
base/7/x86_64                                                           CentOS-7 - Base                                                            9,591
extras/7/x86_64                                                         CentOS-7 - Extras                                                            283
updates/7/x86_64                                                        CentOS-7 - Updates                                                         1,134
repolist: 11,008
[root@ip-10-1-2-173 centos]# /etc/yum.repos.d
bash: /etc/yum.repos.d: Is a directory
[root@ip-10-1-2-173 centos]# ll /etc/yum.repos.d
total 28
-rw-r--r--. 1 root root 1664 Aug 30 10:53 CentOS-Base.repo
-rw-r--r--. 1 root root 1309 Aug 30 10:53 CentOS-CR.repo
-rw-r--r--. 1 root root  649 Aug 30 10:53 CentOS-Debuginfo.repo
-rw-r--r--. 1 root root  314 Aug 30 10:53 CentOS-fasttrack.repo
-rw-r--r--. 1 root root  630 Aug 30 10:53 CentOS-Media.repo
-rw-r--r--. 1 root root 1331 Aug 30 10:53 CentOS-Sources.repo
-rw-r--r--. 1 root root 3830 Aug 30 10:53 CentOS-Vault.repo

