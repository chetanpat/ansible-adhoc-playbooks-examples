### Ansible-AdHoc-Commands

#### Run operations in the background mode  
Some operations take a lot of time to finish (minutes or even hours). For example, when you run `yum update` or `apt-get update && apt-get dist-upgrade`, it could be a few minutes before all the packages on your servers are updated. In these situations, you can tell Ansible to run the commands asynchronously, and poll the servers to see when the commands finish.

#### To run a command in the background, you set the following options: 
1. -B <seconds>: the maximum amount of time (in seconds) to let the job run. 
1. -P <seconds>: the amount of time (in seconds) to wait between polling the servers for an updated job status.
```
$ ansible all -b -B 3600 -P 0 -a "yum update -y"
```

#### Update servers asynchronously with asynchronous jobs Let’s run `yum -y update` on all our servers to get them up to date. If you set -P 0, Ansible fires off the command on the servers, then prints the background job information to the screen and exits:
While the background task is running, you can check on the status elsewhere using Ansible’s async_status module, as long as you have the ansible_job_id value to pass in as jid: 
```
$ ansible all -b -m async_status -a "jid=1234.1234"
```


