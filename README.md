# K8s_playbook

![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/Hijinko/k8s_playbook)
![GitHub repo size](https://img.shields.io/github/repo-size/Hijinko/k8s_playbook)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/Hijinko/k8s_playbook)
![GitHub contributors](https://img.shields.io/github/contributors/Hijinko/k8s_playbook)


k8s_playbook is an Ansible playbook that allows developers to easily set up a kubernetes cluster and install common needed tools for administration and development.

Additional line of information text about what the project does. Your introduction should be around 2 or 3 sentences. Don't go overboard, people won't read it.

## Prerequisites

Before you begin, ensure you have met the following requirements:
* You have installed Ansible on a controller machine
* You have atleast one Ubuntu server to install kubernetes on
* Your Ansible controller can ssh from ubuntu hosts in the cluster

To run the k8s_playbook, follow these steps:

Ansible controller generate ssh key and copy it to the host master-node as user joe
```
ssh-keygen
ssh-copy-id joe@master-node
```

Ansible conroller edit the inventory file with the correct information in the variables k8s_user and k8s_group and the groups  master and nodes. Also update the my_domain variable to give your services the proper domain or else you will need to manually update the value later using kubectl edit.
Note: If running k8s on a single machine remove the hosts under nodes and update the host under master

## Using k8s_playbook

To use k8s_playbook, follow these steps after updating the inventory file

```
ansible-playbook playbook.yml -K
```
