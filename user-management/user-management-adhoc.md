# Ansible-AdHoc-Commands

## Manage users and groups

### Add an admin group on the servers for the server administration: 
```
$ ansible all -b -m group -a "name=admin state=present gid=1234 system=yes"
```
### Add the user john to the servers with the group I just created and give him a home folder in /home/john
```
$ ansible all -b -m user -a "name=john group=admin uid=1234 shell=/bin/bash password=ansadmin createhome=yes generate_ssh_key=yes"
```
### What if you want to delete the account?
```
$ ansible all -b -m user -a "name=john state=absent remove=yes"
```