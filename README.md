# Ceph4.1-installation
======================

This playbook is to install the ceph-storage. It consists of three roles as below:
1. ceph_pre_deployment : This role will validate all the pre-requisites.
2. ceph_ansible_deployment: This role will validate ceph installer VM and install ceph
3. ceph_post_deployment : This role will create pools and create the ceph external file.

Dependencies
------------

These are Python requirements needed to run ceph Deployment
- ansible>=2.9,<2.10,!=2.9.10
- netaddr
------------
# How to execute:
### Step1) create passwd.yml
Create passwd.yml file and set the root username and password for the ceph nodes
ansible-vault create passwd.yml
update vault file
ansible-vault edit passwd.yml

### Step2) prepare ceph_input.json file
Create/Edit/Update the ceph_input.json file or fetch the same from LLD portal.
Place this json file inside the template folder
./template/ceph_input.json

### Steps3) Execute the ansible playbook
```
anisble-playbook main.yml -e "@passwd.yml" --ask-vault-pass
```
