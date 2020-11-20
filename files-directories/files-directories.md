# Ansible-AdHoc-Commands

## Manage files and directories

### Copy Module
```
$ ansible all -b -m copy -a "src=/tmp/sample.txt dest=/home/ansadmin/"
```
### Shell Module: The shell module commands are run in /bin/sh shell and you can make use of the operators like ‘>’ or ‘|’ (pipe symbol or even environment variables.
```
$ ansible all -b -m shell -a 'ls-la>temp.txt'
```
### Command Module: On the machines under webservers group check for the file created and run the command to view the text file.
```
$ ansible all -b -m command -a "cat temp.txt"
```
### File Module: This module is used to create files, directories, set, or change file permissions and ownership etc
#### File Creation
```
$ ansible all -b -m file -a "dest=/tmp/sample.txt state=touch mode=600 owner=ansadmin group=ansadmin"
```
```
$ ansible all -b -m file -a "dest=/tmp/sample.txt state=absent"
#### Directory Creation
```
$ ansible all -b -m file -a "dest/tmp/sample state=directory mode=600 owner=ansadmin group=ansadmin"
```
### Fetch Module: Transfer the files from Managed nodes to Controller 
```
$ ansible all -b -m fetch -a "src=/tmp/sample dest=/tmp/
```





