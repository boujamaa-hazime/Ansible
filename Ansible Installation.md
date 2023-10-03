### Install Ansible:
```bash
sudp apt install ansible
```

### Inventory:
```bash
nano inventory
# hre we will ad all the IPs or name of servers we will use
```

### first use of ansible:
```bash
ansible all --key-file ~/.ssh/ansible -i inventory -m ping
```

### creay an ansible.cfg file where all in is is set :
```bash
#ansible.cfg file
[defaults]
inventory = inventory
private_key_file = ~/.ssh/ansible
```

after that we go to the directory where the file is ans we excute :
```bash
ansible all -m ping
```

---------------------------------------
# Getting started with Ansible 05 - Running elevated ad-hoc Commands

### Tell ansible to use sudo (become)
on this case become is the sudo also we asked to ask for password for he can run 
```bash
ansible all -m apt -a update_cache=true --become --ask-become-pass
```
### Install a package via the apt module:
```bash
ansible all -m apt -a name=vim-nox --become --ask-become-pass
```
### Install a package via the apt module, and also make sure it’s the latest version available
``` bash
ansible all -m apt -a "name=snapd state=latest" --become --ask-become-pass
```
### Upgrade all the package updates that are available
```bash
ansible all -m apt -a upgrade=dist --become --ask-become-passxx
```