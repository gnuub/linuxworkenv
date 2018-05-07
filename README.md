# linuxworkenv
---
Ansible Playbook for a yum managed server or workstation to make the following updates:
* Install latest "tree" filesystem viewer utility
* Install latest "tmux" terminal utility
* Install latest "Vim" editor
* Configure Vim environment
* Configure bash environment

This playbook is intended to be used as a base for automated work environment configuration in a RHEL environment.
Some Ansible know-how can easily extend this to add more apps and update different configuration files to suit your needs. 

To use, git clone the repo to your Ansible Control Server.  Alternatively, you can download it directly from the repo then copy the project
to your Ansible Control Server. Update the inventory file with the host(s) and user informaiton. The playbook expects to update all hosts found under
the [workstations] group. The playbook also expects the *user* variable and it should be the login you use for ssh and the *profile* variable which
is your login id (basically both variables should match). You will need sudo access for yum.

#### File Tree
```
.
├── ansible.cfg
├── files
│   ├── bash_profile
│   ├── tmux.conf
│   └── vimrc
├── inventory
├── linuxworkenv.yml
└── README.md
```

Invoke the playbook as follows:
```
ansible-playbook linuxworkenv.yml --ask-become-pass
```
