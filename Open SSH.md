### 1 - To find your IP
```bash
ip p
```

### 2- Generate an SSH Key 
```bash
ssh-keygen -t ed25519 -C "jay default"
```
t: type of the encryption 
c: comment 

### 3- copy SSH key to the targets 
```bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub 172.16.250.133
```

### 4- choose which one of keys i will use 
```bash
ssh -i ~/.ssh/ansible IP_Target
```

### 5- check or catch the passphrase once 
```bash
eval $(ssh-agent)

# this comand will add the passphrase to it 
SSH-add
```

### 6- alias command 
```bash
alias ssha='eval $(ssh-agent) && ssh-add'

#now i can use ssha as a command 
ssha
```

7- more
```bash
# this command is used for make changes on the script and add an alias 
nano .bashrc 
```