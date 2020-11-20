# Ansible-AdHoc-Commands

## Packages Installation

### Git Installation: If you want to install a generic package like git on any Debian, RHEL, Fedora, Ubuntu, CentOS, FreeBSD, etc. system, you can use the command:
```
$ ansible all -b -m yum -a "name=git state=present"
```
### Check if the package is installed & update it to the latest version.
```
$ ansible all -b -m yum -a "name=git state=latest"
```
### Maven Installation
```
$ ansible all -b -m yum -a "name=maven state=present"
```
### httpd Installation
```
$ ansible all -b -m yum -a "name=httpd state=present"
```
### Managing Services Module: To manage services with ansible, we use a module ‘service’.

#### Starting a service
```
$ ansible all -b -m service -a "name=httpd state=started"
```
#### Stopping a service
```
$ ansible all -b -m service -a "name=httpd state=stopped"
```
#### Restarting a service
```
$ ansible all -b -m service -a "name=httpd state=restarted"
```

