# linuxworkenv
---
Ansible Playbook for a yum managed server or workstation to make the following updates:
* Install latest "tree" filesystem viewer utility
* Install latest "tmux" terminal utility
* Install latest "Vim" editor
* Configure Vim environment
* Configure bash environment

This playbook is intended to be used as a base for easy work environment configuration in a RHEL environment.
Some Ansible know-how can easily extend this to add more apps and configuration file appends to suit your needs. 

To use, git clone the repo to your Ansible Control Server or download it directly from the repo then copy the Ansible project
to your Ansible Control Server. Be sure to update the inventory file with host(s) to update. 
Update the variables to your information like your profile name.

#### File Tree
```
.
├── ansible.cfg
├── files
│   ├── bash_profile
│   └── vimrc
├── inventory
├── linuxworkenv.yml
└── README.md
```

You will need sudo access for yum.  Invoke the playbook as follows:
```
ansible-playbook linuxworkenv.yml --ask-become-pass
```
