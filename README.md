# Vanaheim
EC2 Ansible inventory to install [Fenrir.](https://github.com/ndoit/fenrir) Feel
free to fork this and change it according to your needs.

This uses a ansible PULL mode to run configuration.

### Prerequisites
The EC2 instance needs
- ansible
- git
- "localhost" on `/etc/ansible/hosts`

This should all be taken care of with user-data on EC2 launch using [this script](https://gist.github.com/RyanSnodgrass/4d9388529dcb4ace09f880ce414c7ed9)

The only thing it needs that the script can't handle is installing the RVM
ansible role. For that run `ansible-galaxy install rvm_io.ruby`

### Usage
Run this on the EC2 instance you need to configure.
```
$ ansible-pull -U https://github.com/ndoit/vanaheim
```
