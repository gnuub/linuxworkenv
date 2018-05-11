# linuxworkenv
---
Ansible Playbook for a yum managed server or workstation to make the following updates:
* Install latest "tree" filesystem viewer utility
* Install latest "tmux" terminal utility
* Install latest "Vim" editor
* Configure Vim environment
* Configure bash environment
* Configure tmux environment

This playbook is intended to be used as a base for deploying a consistent work environment configuration on a RHEL system through automation so to be iterable and predictable. 
Some Ansible know-how can easily extend this to add more apps and update different configuration files to suit your needs. 

To use, git clone the repo to your Ansible Control Server.
Alternatively, you can download it directly from the repo then copy the project to your Ansible Control Server.
Update the inventory file with the host(s) informaiton under the [workstations] group.
Thist playbook is written to act against the [worksations] group found in the inventory file.
The playbook expects the *user* variable to be given as a parameter in the command line or will fail. 
This is the user account you are using to access all the hosts under the [workstations] group.
The account you use will need sudo access for yum.
Please see examples at the bottom. 

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

If you have exchanged keys with the remote hosts, invoke the playbook as follows:
```
ansible-playbook -i ~/inventory -C -D --limit=catl0xlas00423.corp.cox.com linuxworkenv.yml --ask-become-pass -e 'user=<username>'
```

If you have have not exchanged keys with the remote hosts, invoke the playbook as follows:
```
ansible-playbook -i ~/inventory -C -D --limit=catl0xlas00423.corp.cox.com linuxworkenv.yml --ask-become-pass -e 'user=<username>' -k
```
