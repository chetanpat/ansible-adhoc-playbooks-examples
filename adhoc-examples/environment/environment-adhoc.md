### Ansible-AdHoc-Commands

### Environment
#### Use ansible with the -a argument ‘hostname’ to run hostname against all the servers: 
```
$ ansible all -a "hostname"
```
#### Run the same command again, but this time, add the argument -f 1 to tell Ansible to use only one fork (basically, to perform the command on each server in sequence):
```
$ ansible all -a "hostname" -f 1
```
#### Disk space available for our application:
```
$ ansible all -a "df -h"
```
#### Enough memory on our servers: 
```
$ ansible all -a "free -m"
```
#### Date and time on each server is in sync: 
```
$ ansible all -a "date"
```
#### We want to install the chrony daemon on the server to keep the time in sync.Instead of running the command yum install -y chrony on each of the servers, we’ll use ansible’s yum module to do the same
```
$ ansible all -b -m yum -a "name=chrony state=present"
```
#### Now we’ll make sure the chrony daemon is started and set to run on boot. We could use two separate commands, systemctl start chronyd and systemctl enable chronyd, but we’ll use Ansible’s service module instead. 
```
$ ansible all -b -m service -a "name=chronyd state=started enabled=yes"
```
#### Make sure our servers are synced closely to the official time on a time server:
```
$ ansible all -a "chronyc tracking" -b
```
