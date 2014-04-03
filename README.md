Ansible II
###Collects facts about the hosts
ansible all -m setup -i hosts -u root

###Copy a file
ansible dbservers -m copy -a "src=/path/tofile dest=/path/to/dest"

###Cloning a git repo to a path.
ansible appservers -m git -a "repo=https://.... dest=/home/user/ansible"

### Create users
ansible all -m user -a "user=www-data state=present" -i hosts -u root

### Install a package
ansible centos -m yum -a "name=nginx state=present" -i hosts -u root

### Start a service
ansible all -m service -a "name=nginx state=started" -i hosts -u root	

### Enable a service
ansible all -m service -a "name=nginx enabled=yes" -i hosts -u root