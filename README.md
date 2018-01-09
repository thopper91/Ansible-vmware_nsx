<img src="https://blogs.vmware.com/networkvirtualization/files/2015/08/VMW-NSX-Logo1.jpg" width="200"/>

# Ansible-vmware_nsx

This repository contains a handful of playbooks to assist in completing a couple of taks for vmware NSX.

## Current Pre-requisites
As it currently is, it is assumed you have a vmware vcentre deployed along with a nsx instance.

## Documentation
All additional documentations will be uploaded to the repositories Wiki:

[Home of the Wikis](https://github.com/thopper91/Ansible-vmware_nsx/wiki)

### Additional GitHub help
- ['afewell' Ansible labs](https://github.com/afewell/AnsibleNSX101)
- [vmware nsxansible repository](https://github.com/vmware/nsxansible)

## How do I run these playbooks? 
Well first, what ever tasks need to be run, then we need to ensure the "Ensure_config_file_updated" role is included as the first one. This will update the config file to add a line to put a path in for the nsxansible repository.
Then once the playbooks are ready to be ran: 
```
$ ansible-playbook FILENAME.yml --extra-vars "ansible_sudo_pass=PASSWORD"
```
- FILENAME: The name of the ansible playbook you want to run
- PASSWORD: The sudo password to this machine

The ansible line of code runs the playbook with an additional variable for a password. This password is the VM's/Machine's 
password. We have to include these due to stating we will become sudo with this line of code
``` become: true ```
