### Ansible-AdHoc-Commands

#### Deploy a version-controlled application
For simple application deployments, where you may need to update a git checkout, or copy a new bit of code to a group of servers, then run a command to finish the deployment, Ansible’s ad-hoc mode can help.

In the example below, I’ll assume we’re running a simple application on one or two servers, in the directory /opt/myapp. This directory is a git repository cloned from a central server or a service like GitHub, and application deployments and updates are done by updating the clone at /opt/myapp/

#### Note: Don't use the become or -b flag if you're cloning with a specific user
 
```
$ ansible all -m git -a "repo=git://example.com/path/to/repo.git dest=/opt/myapp update=yes"
```

