# Vanaheim
EC2 Ansible inventory to install [Fenrir.](https://github.com/ndoit/fenrir) Feel
free to fork this and change it according to your needs.

This uses a Ansible PULL mode to run configuration on a fresh EC2 instance.

### Prerequisites
The EC2 instance needs
- Ansible
- git
- rvm1-ansible ansible role
- "localhost" on `/etc/ansible/hosts`
- ansible-vault password

This should all be taken care of with user-data on EC2 launch using [this script](https://gist.github.com/RyanSnodgrass/4d9388529dcb4ace09f880ce414c7ed9)

If you have already started up an EC2 instance, you can still run the script. The
only caveat is it has to all be run as root as that's how the user-data is run.

The ansible vault password is on password safe. To use it create a file called
`.vault_pass.txt` in the home `~` directory and put the password as the only
entry in it. The usage command will look in that file and use that for decryption.

### Usage
Run this on the EC2 instance you need to configure.
```
$ ansible-pull -U https://github.com/ndoit/vanaheim --vault-password-file ~/.vault_pass.txt
```
