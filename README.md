# linuxworkenv
---
Ansible Playbook to update a yum managed server or workstation with a custom Vim environment, bash 
environment variables, "tree" filesystem viewer utility, and "tmux" terminal utility.

To use, git close the repo to your Ansible Control Server.
Update the inventory file with host(s) to update.
Update the variables to your information like your profile name.

You will need sudo access for yum.  Invoke the playbook as follows:
'''
ansible-playbook linuxworkenv.yml --ask-become-pass
'''
