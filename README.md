---
tags:
  - ansible
  - beginner
  - codespaces
---

# Ansible - Collect Configs


In this lab, you will write an Ansible playbook to back up configurations of network devices. You will work with a provided topology of four routers set up with Netlab. The inventory is preconfigured to get you started quickly.

!!! tip

    The lab can be run with [GitHub Codespaces](https://github.com/codespaces/new?ref=main&repo=837679935). For information on how to run the netlab topology on your infrastructure, take a look at [netlab](https://netlab.tools/install/).

## Inventory

The inventory is prepared, but if you change the device types or the topology, you will need to update the inventory accordingly. You can inspect the inventory using `ansible-inventory`.

``` titel="ansible-inventory -i inventory.yaml --graph --vars"
@all:
  |--@routers:
  |  |--@cumulus:
  |  |  |--r1
  |  |  |  |--{ansible_host = 172.20.20.3}
  |  |  |  |--{ansible_password = root}
  |  |  |  |--{ansible_user = root}
  |  |  |--{ansible_password = root}
  |  |  |--{ansible_user = root}
  |  |--@frr:
  |  |  |--r2
  |  |  |  |--{ansible_host = 172.20.20.3}
  |  |--@srlinux:
  |  |  |--r4
  |  |  |  |--{ansible_connection = ansible.netcommon.httpapi}
  |  |  |  |--{ansible_host = 172.20.20.3}
  |  |  |  |--{ansible_network_os = nokia.srlinux.srlinux}
  |  |  |  |--{ansible_password = NokiaSrl1!}
  |  |  |  |--{ansible_user = admin}
  |  |  |--{ansible_connection = ansible.netcommon.httpapi}
  |  |  |--{ansible_network_os = nokia.srlinux.srlinux}
  |  |  |--{ansible_password = NokiaSrl1!}
  |  |  |--{ansible_user = admin}
  |  |--@vyos:
  |  |  |--r3
  |  |  |  |--{ansible_host = 172.20.20.3}
  |  |  |  |--{ansible_network_os = vyos}
  |  |  |  |--{ansible_ssh_pass = vyos}
  |  |  |  |--{ansible_user = vyos}
  |  |  |--{ansible_network_os = vyos}
  |  |  |--{ansible_ssh_pass = vyos}
  |  |  |--{ansible_user = vyos}
  |--@ungrouped:
```

## Playbook

The goal of the exercise is to write an Ansible playbook that automates the backup of all router configurations in the provided topology. The [Discussions on the GitHub Repo](https://github.com/NetAutLabs/ansible_collect_configs/discussions) can be used to discuss the lab and your solutions. 
