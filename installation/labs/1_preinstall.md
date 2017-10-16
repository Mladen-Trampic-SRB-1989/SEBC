1. Check `vm.swappiness` on all your nodes

```
vi private_IPs.txt

172.31.36.238
172.31.34.41
172.31.39.153
172.31.46.152
172.31.34.191
```

Swappiness on nodes:

```
[centos@ip-172-31-36-238 ~]$ cat private_IPs.txt | while read line; do ssh $line 'echo `hostname` && cat /proc/sys/vm/swappiness' </dev/null; done
ip-172-31-36-238
1
ip-172-31-34-41
30
ip-172-31-39-153
30
ip-172-31-46-152
30
ip-172-31-34-191
30
```

* Set the value to `1` if necessary

```
[centos@ip-172-31-36-238 ~]$ cat private_IPs.txt | while read line; do
ssh -tt $line << 'EOF'
sudo sysctl vm.swappiness=1
echo "vm.swappiness=1" | sudo tee --append /etc/sysctl.conf
exit
EOF
done
```

2. Show the mount attributes of all volumes

```
[centos@ip-172-31-34-191 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599028k,nr_inodes=1899757,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda1 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=28,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
nfsd on /proc/fs/nfsd type nfsd (rw,relatime)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)
/dev/xvdb1 on /1 type ext4 (rw,noatime,seclabel,data=ordered)
/dev/xvdc1 on /2 type ext4 (rw,noatime,seclabel,data=ordered)
```

4. Disable transparent hugepage support

Created systemd service, /etc/systemd/system/disable-transparent-huge-pages.service
With content:
```
[Unit]
Description=Disable Transparent Huge Pages
Documentation=https://redis.io/topics/latency

[Service]
Type=oneshot
ExecStart=/usr/bin/sh -c "/usr/bin/echo 'never' > /sys/kernel/mm/transparent_hugepage/enabled"
ExecStart=/usr/bin/sh -c "/usr/bin/echo 'never' > /sys/kernel/mm/transparent_hugepage/defrag"

[Install]
WantedBy=multi-user.target
```

After which daemon-reloaded, enabled on boot, and started.

```
[root@ip-172-31-34-238 ~]# systemctl daemon-reload
[root@ip-172-31-34-238 ~]# systemctl enable disable-transparent-huge-pages.service
[root@ip-172-31-34-238 ~]# systemctl start disable-transparent-huge-pages.service
```

Verifying:
```
[root@ip-172-31-36-238 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]
[root@ip-172-31-36-238 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
```

5. List your network interface configuration

```
[root@ip-172-31-36-238 ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 06:66:93:43:e5:22 brd ff:ff:ff:ff:ff:ff
    inet 172.31.36.238/20 brd 172.31.47.255 scope global dynamic eth0
       valid_lft 2853sec preferred_lft 2853sec
    inet6 fe80::466:93ff:fe43:e522/64 scope link
       valid_lft forever preferred_lft forever

```

6. List forward and reverse host lookups using getent or nslookup
```
[root@ip-172-31-36-238 ~]# getent hosts ec2-18-196-2-63.eu-central-1.compute.amazonaws.com
172.31.36.238   ec2-18-196-2-63.eu-central-1.compute.amazonaws.com
[root@ip-172-31-36-238 ~]# getent hosts ec2-54-93-121-7.eu-central-1.compute.amazonaws.com
172.31.39.153   ec2-54-93-121-7.eu-central-1.compute.amazonaws.com
[root@ip-172-31-36-238 ~]# getent hosts ec2-35-159-24-106.eu-central-1.compute.amazonaws.com
172.31.34.41    ec2-35-159-24-106.eu-central-1.compute.amazonaws.com
[root@ip-172-31-36-238 ~]# getent hosts ec2-54-93-231-189.eu-central-1.compute.amazonaws.com
172.31.46.152   ec2-54-93-231-189.eu-central-1.compute.amazonaws.com
[root@ip-172-31-36-238 ~]# getent hosts ec2-54-93-234-85.eu-central-1.compute.amazonaws.com
172.31.34.191   ec2-54-93-234-85.eu-central-1.compute.amazonaws.com
```
7. Show the nscd service is running
yum install -y nscd
systemctl enable nscd
systemctl start nscd

```
[root@ip-172-31-36-238 ~]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-16 14:51:38 UTC; 45s ago
  Process: 17894 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 17895 (nscd)
   CGroup: /system.slice/nscd.service
           └─17895 /usr/sbin/nscd

Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 monitoring directory `/etc` (2)
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 monitoring file `/etc/resolv.conf` (5)
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 monitoring directory `/etc` (2)
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 monitoring file `/etc/services` (6)
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 monitoring directory `/etc` (2)
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Oct 16 14:51:38 ip-172-31-36-238 nscd[17895]: 17895 Access Vector Cache (AVC) started
Oct 16 14:51:38 ip-172-31-36-238 systemd[1]: Started Name Service Cache Daemon.
Oct 16 14:51:57 ip-172-31-36-238 nscd[17895]: 17895 checking for monitored file `/etc/netgroup': No such file or directory
```

8.Show the ntpd service is running
yum install -y ntp
systemctl enable ntpd
systemctl start ntpd

```
[root@ip-172-31-36-238 ~]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-16 14:51:35 UTC; 1min 46s ago
 Main PID: 17888 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─17888 /usr/sbin/ntpd -u ntp:ntp -g

Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: Listen normally on 3 eth0 172.31.36.238 UDP 123
Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: Listen normally on 4 lo ::1 UDP 123
Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: Listen normally on 5 eth0 fe80::466:93ff:fe43:e522 UDP 123
Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: Listening on routing socket on fd #22 for interface updates
Oct 16 14:51:35 ip-172-31-36-238 systemd[1]: Started Network Time Service.
Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: 0.0.0.0 c016 06 restart
Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 16 14:51:35 ip-172-31-36-238 ntpd[17888]: 0.0.0.0 c011 01 freq_not_set
Oct 16 14:51:42 ip-172-31-36-238 ntpd[17888]: 0.0.0.0 c614 04 freq_mode
Oct 16 14:53:14 ip-172-31-36-238 systemd[1]: Started Network Time Service.
```