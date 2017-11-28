1. Check vm.swappiness on all your nodes
<code>
sudo su
#echo 1 > /proc/sys/vm/swappiness
#echo "vm.swappiness = 1" >> /etc/sysctl.conf
<code>

*Screenshot

![Alt text](/SEBC/labs/images/swapiness.png?raw=true "Swapiness")
