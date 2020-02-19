# Kubernetes Cluster with Ansible

## Introduction
Ansible scripts to set-up simple kubernetes with kubeadm. I have tested this on both CentOS7 and Ubuntu 16.04

## Preparation
The set up consists of 1 x master node and 2 x worker node in AWS. Ensure all these resources are in place.

If you are running on a fresh VMs , remember to create the intiial users 'ubuntu' or 'centos' first.

## Steps

1) Run the initial setup to install required dependencies

```
ansible-playbook -i inventory/hosts initial.yml
```

2) Install and configure kubernetes packages

```
ansible-playbook -i inventory/hosts kubernetes.yml
```

3) Initial cluster and configure the master node

```
ansible-playbook -i inventory/hosts master.yml
```

4) Configure worker nodes and join cluster

```
ansible-playbook -i inventory/hosts workers.yml
```

## Acknowledgments
* [k8 cluster with Ansible](https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-18-04/) - How To Create a Kubernetes Cluster Using Kubeadm on Ubuntu 18.04
