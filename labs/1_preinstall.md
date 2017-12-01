<!-- CSS work goes here for the time being -->
<!-- set a:link text-decoration to none -->
<!-- set a:hover text-decoration to underline -->
<!-- http://forums.markdownpad.com/discussion/143/include-pdf-pagebreak-instructions-in-markdown/p1 -->
<!-- <script src="https://cdn.rawgit.com/google/code-prettify/master/loader/run_prettify.js"></script> -->

---
<div style="page-break-after: always;"></div>

# <center>CM Install Lab 
## <center> Preinstall

<strong>1. Check vm.swappiness on all your nodes</strong>
<pre class="prettyprint">
$sudo su
#echo 1 > /proc/sys/vm/swappiness
#echo "vm.swappiness = 1" >> /etc/sysctl.conf
</pre>
*Screenshot
![Alt text](https://github.com/alexpg06/SEBC/blob/master/labs/images/swapiness.png "Swapiness")

<strong>2. Mount attributes of your volume(s)</strong>
<pre class="prettyprint">
# /etc/fstab
# Created by anaconda on Tue Sep 12 23:48:48 2017
#
# Accessible filesystems, by reference, are maintained under '/dev/disk'
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
#
UUID=0356e691-d6fb-4f8b-a905-4230dbe62a32 /                       xfs     defaults        0 0
/dev/xvdb1  /disk1   ext4 defaults 1 2
/dev/xvdc1  /disk2   ext4 defaults 1 2
</pre>

<strong>3. List the reserve space setting of the volumes</strong>
<pre class="prettyprint">
sudo su
#fdisk /dev/xvdb
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table
Building a new DOS disklabel with disk identifier 0xb200bab6.

Command (m for help): n
Partition type:
   p   primary (0 primary, 0 extended, 4 free)
   e   extended
Select (default p): p
Partition number (1-4, default 1): 1
First sector (2048-251658239, default 2048): 
Using default value 2048
Last sector, +sectors or +size{K,M,G} (2048-251658239, default 251658239): 
Using default value 251658239
Partition 1 of type Linux and of size 120 GiB is set

Command (m for help): w
The partition table has been altered!

Calling ioctl() to re-read partition table.
Syncing disks.
[root@ip-10-1-2-143 centos]# mke2fs -t ext4 /dev/xvdb1
mke2fs 1.42.9 (28-Dec-2013)
Filesystem label=
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
7864320 inodes, 31457024 blocks
1572851 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=2178940928
960 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
	4096000, 7962624, 11239424, 20480000, 23887872

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done   

[root@ip-10-1-2-143 centos]# tune2fs -m 0 /dev/xvdb1
tune2fs 1.42.9 (28-Dec-2013)
Setting reserved blocks percentage to 0% (0 blocks)
Setting reserved blocks percentage to 0% (0 blocks)
[root@ip-10-1-2-143 centos]# mkdir /disk1
[root@ip-10-1-2-143 centos]# mount /disk1
</pre>

<strong>4. Disable transparent hugepage support</strong>
<pre class="prettyprint">
[root@ip-10-1-2-143 centos#echo never > /sys/kernel/mm/transparent_hugepage/defrag
[root@ip-10-1-2-143 centos#echo never > /sys/kernel/mm/transparent_hugepage/enable
[root@ip-10-1-2-143 centos#vi /etc/rc.local
#!/bin/bash
# THIS FILE IS ADDED FOR COMPATIBILITY PURPOSES
#
# It is highly advisable to create own systemd services or udev rules
# to run scripts during boot instead of using this file.
#
# In contrast to previous versions due to parallel execution during boot
# this script will NOT be run after all other services.
#
# Please note that you must run 'chmod +x /etc/rc.d/rc.local' to ensure
# that this script will be executed during boot.

touch /var/lock/subsys/local

echo never > /sys/kernel/mm/transparent_hugepage/defrag
echo never > /sys/kernel/mm/transparent_hugepage/enabled
</pre>

<strong>5. List your network interface configuration</strong>
<pre class="prettyprint">
[centos@ip-10-1-2-181 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.1.2.181  netmask 255.255.255.128  broadcast 10.1.2.255
        inet6 fe80::c18:d2ff:fe47:a69c  prefixlen 64  scopeid 0x20<link>
        ether 0e:18:d2:47:a6:9c  txqueuelen 1000  (Ethernet)
        RX packets 10028446  bytes 6868563506 (6.3 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 7139311  bytes 76873176030 (71.5 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 14344826  bytes 24247347597 (22.5 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 14344826  bytes 24247347597 (22.5 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
</pre>

<strong>6. Show that forward and reverse host lookups are correctly resolved</strong>
<pre class="prettyprint">
[centos@ip-10-1-2-181 ~]$ getent hosts ip-10-1-2-143.ec2.internal
10.1.2.143      ip-10-1-2-143.ec2.internal
[centos@ip-10-1-2-181 ~]$ nslookup
> ip-10-1-2-143.ec2.internal
Server:		10.1.2.2
Address:	10.1.2.2#53

Non-authoritative answer:
Name:	ip-10-1-2-143.ec2.internal
Address: 10.1.2.143
</pre>

<strong>7. Show the nscd service is running</strong>
<pre class="prettyprint">
[root@ip-10-1-2-181 centos]# service nscd status
Redirecting to /bin/systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-11-28 12:00:34 CST; 2 days ago
 Main PID: 714 (nscd)
   CGroup: /system.slice/nscd.service
           └─714 /usr/sbin/nscd

Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitored file `/etc/group` was moved into place, adding watch
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring file `/etc/passwd` (63)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring directory `/etc` (2)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring file `/etc/group` (64)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring directory `/etc` (2)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring file `/etc/passwd` (63)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring directory `/etc` (2)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring file `/etc/group` (64)
Nov 30 10:49:52 ip-10-1-2-181.ec2.internal nscd[714]: 714 monitoring directory `/etc` (2)
</pre>


<strong>8. Show the ntpd service is running</strong>
<pre class="prettyprint">
[root@ip-10-1-2-181 centos]# service ntpd status
Redirecting to /bin/systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-11-28 16:59:00 CST; 2 days ago
 Main PID: 20607 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─20607 /usr/sbin/ntpd -u ntp:ntp -g

Nov 28 16:59:00 ip-10-1-2-181.ec2.internal ntpd[20607]: Listen normally on 4 lo ::1 UDP 123
Nov 28 16:59:00 ip-10-1-2-181.ec2.internal ntpd[20607]: Listen normally on 5 eth0 fe80::c18:d2ff:fe47:a69c UDP 123
Nov 28 16:59:00 ip-10-1-2-181.ec2.internal ntpd[20607]: Listening on routing socket on fd #22 for interface updates
Nov 28 16:59:00 ip-10-1-2-181.ec2.internal systemd[1]: Started Network Time Service.
Nov 28 16:59:01 ip-10-1-2-181.ec2.internal ntpd[20607]: 0.0.0.0 c016 06 restart
Nov 28 16:59:01 ip-10-1-2-181.ec2.internal ntpd[20607]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Nov 28 16:59:01 ip-10-1-2-181.ec2.internal ntpd[20607]: 0.0.0.0 c011 01 freq_not_set
Nov 28 16:59:07 ip-10-1-2-181.ec2.internal ntpd[20607]: 0.0.0.0 c614 04 freq_mode
Nov 28 17:19:11 ip-10-1-2-181.ec2.internal ntpd[20607]: 0.0.0.0 0612 02 freq_set kernel -19.676 PPM
Nov 28 17:19:11 ip-10-1-2-181.ec2.internal ntpd[20607]: 0.0.0.0 0615 05 clock_sync
</pre>
