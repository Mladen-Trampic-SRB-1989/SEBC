* List the cloud provider you are using (AWS, GCE, Azure, other)
```
Amazon Web Services
```
* List the Linux release you have chosen 
```
[root@ip-172-31-41-191 ~]# cat /etc/redhat-release
CentOS Linux release 7.2.1511 (Core)
```
* Show that the disk space on each node is at least 30 GB
  * Node 1
  ```
   [root@ip-172-31-34-39 ~]# df -hT
   Filesystem     Type      Size  Used Avail Use% Mounted on
   /dev/xvda1     xfs        30G  930M   30G   4% /
   devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
   tmpfs          tmpfs     7.2G     0  7.2G   0% /dev/shm
   tmpfs          tmpfs     7.2G   17M  7.2G   1% /run
   tmpfs          tmpfs     7.2G     0  7.2G   0% /sys/fs/cgroup
   tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0
   /dev/xvdb1     ext4       37G   49M   35G   1% /1
   /dev/xvdc1     ext4       37G   49M   35G   1% /2
  ```
  * Node 2
  ```
   [root@ip-172-31-38-249 ~]# df -hT
   Filesystem     Type      Size  Used Avail Use% Mounted on
   /dev/xvda1     xfs        30G  877M   30G   3% /
   devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
   tmpfs          tmpfs     7.2G     0  7.2G   0% /dev/shm
   tmpfs          tmpfs     7.2G   17M  7.2G   1% /run
   tmpfs          tmpfs     7.2G     0  7.2G   0% /sys/fs/cgroup
   tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0
   /dev/xvdb1     ext4       37G   49M   35G   1% /1
   /dev/xvdc1     ext4       37G   49M   35G   1% /2
  ```
  * Node 3
  ```
   [root@ip-172-31-43-139 ~]# df -hT
   Filesystem     Type      Size  Used Avail Use% Mounted on
   /dev/xvda1     xfs        30G  877M   30G   3% /
   devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
   tmpfs          tmpfs     7.2G     0  7.2G   0% /dev/shm
   tmpfs          tmpfs     7.2G   17M  7.2G   1% /run
   tmpfs          tmpfs     7.2G     0  7.2G   0% /sys/fs/cgroup
   tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0
   /dev/xvdb1     ext4       37G   49M   35G   1% /1
   /dev/xvdc1     ext4       37G   49M   35G   1% /2
  ```
  * Node 4
  ```
   [root@ip-172-31-41-191 ~]# df -hT
   Filesystem     Type      Size  Used Avail Use% Mounted on
   /dev/xvda1     xfs        30G  877M   30G   3% /
   devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
   tmpfs          tmpfs     7.2G     0  7.2G   0% /dev/shm
   tmpfs          tmpfs     7.2G   17M  7.2G   1% /run
   tmpfs          tmpfs     7.2G     0  7.2G   0% /sys/fs/cgroup
   tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0
   /dev/xvdb1     ext4       37G   49M   35G   1% /1
   /dev/xvdc1     ext4       37G   49M   35G   1% /2
  ```
  * Node 5
  ```
   [root@ip-172-31-40-178 ~]# df -hT
   Filesystem     Type      Size  Used Avail Use% Mounted on
   /dev/xvda1     xfs        30G  877M   30G   3% /
   devtmpfs       devtmpfs  7.3G     0  7.3G   0% /dev
   tmpfs          tmpfs     7.2G     0  7.2G   0% /dev/shm
   tmpfs          tmpfs     7.2G   17M  7.2G   1% /run
   tmpfs          tmpfs     7.2G     0  7.2G   0% /sys/fs/cgroup
   tmpfs          tmpfs     1.5G     0  1.5G   0% /run/user/0
   /dev/xvdb1     ext4       37G   49M   35G   1% /1
   /dev/xvdc1     ext4       37G   49M   35G   1% /2
  ```
* List the command and output for `yum repolist enabled`
```
[root@ip-172-31-34-39 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                                              repo name                                                                                               status
base/7/x86_64                                                                                        CentOS-7 - Base                                                                                         9,591
extras/7/x86_64                                                                                      CentOS-7 - Extras                                                                                         227
updates/7/x86_64                                                                                     CentOS-7 - Updates                                                                                        741
repolist: 10,559
```