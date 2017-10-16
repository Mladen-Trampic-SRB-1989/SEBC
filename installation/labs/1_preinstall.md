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

