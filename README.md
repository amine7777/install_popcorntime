# Popcorn Time playbook [![amine7777](https://circleci.com/gh/amine7777/popcorntime-playbook.svg?style=svg)](https://circleci.com/gh/amine7777/popcorntime-playbook)

----------------------------------


**Popcorn Time playbook**, is an Ansible playbook which install and uninstall easly Popcorn Time software on your linux distribution.


**Popcorn Time**, is a multi-platform, free software BitTorrent client that includes an integrated media player. The applications provide a free "alternative" to subscription-based video streaming services such as Netflix.

**Attention!I am not responsible for your actions. The software in itself is not illegal but the way you use it most likely is.**


## Overview
----------------------------------
![Image description](pop.png)

## Requirements
----------------------------------
- OS Linux with git
- Ansible 2.9



## Installation
---------------------------------

First, you need to install [Ansible](https://www.ansible.com/) on your machine.

```bash
DEBIAN

apt-get update
apt-get install software-properties-common
apt-add-repository ppa:ansible/ansible
apt-get update
apt-get install ansible

REHL

yum install epel-release
yum install Ansible

With pip

pip install ansible
```

Then you need to clone the project and excute the playbook.

```bash
git clone https://github.com/amine7777/install_popcorntime
cd popcorntime-playbook
ansible-playbook deploy_popcorntime.yaml
```

In case you need the 32 bits version, please use this command.

```bash
ansible-playbook deploy_popcorntime.yaml --extra-vars "linux_type=32"
```
## Uninstallation
---------------------------------

In this case you just need to comment the Installation role and uncomment the Uninstallation role. Then, you need to launch the same command.

```yaml
- hosts: localhost
  connection: local
  become: yes
  become_user: root

  roles:
    #- { role: install_popcorntime }
    - { role: uninstall_popcorntime }
```
## Author
----------------------------------
- **Amine Kahlaoui**, DevOps engineer
