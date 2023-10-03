
### Writing our first Playbook
```yml
#install_apache.yml file
 ---
 
 - hosts: all
   become: true
   tasks:
   - name: upadetrepository index
     apt:
       update_cache: yes
   - name: install apache2 package
     apt:
       name: apache2
       state: latest
      #state: absent
   - name: add php support for apache
     apt:
       name: libapache2-mod-php
       state: latest 
      #state: absent this one for unstall what has been installed.
```

### Run the playbook
```bash
 ansible-playbook --ask-become-pass install_apache.yml
```