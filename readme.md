# Ansible playbooks to kickstart VMs on proxmox

This repository contains all the playbooks and files to setup and manage proxmox.

## Getting started

```
# create a venv
python3 -m venv ./venv

source ./venv/bin/activate

# install python requirements
pip install -r requirements.txt

# install neccesary roles and collections
ansible-galaxy install -r requirements.yml
```

To run a playbook:

```
ansible-playbook proxmox.yml

# use --diff to see the changes
# use --check to make a dry runn
ansible-playbook proxmox.yml --check --diff
```

## Installing proxmox

The `proxmox.yml` playbook installs proxmox on a Node, and if configured adds that node to the proxmox cluster. It will also create storage using lvm and lvm-thin.

The `networking.yml` will configure all required bridges and vlan interfaces in a way that proxmox is able to use them.