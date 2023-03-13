# k8s-local-cluster
[![ansible-lint](https://github.com/stackzoo/k8s-local-cluster/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/stackzoo/k8s-local-cluster/actions/workflows/ansible-lint.yml)

Deploy a local multinode k8s cluster with vagrant and ansible 🔧 ☸️

## Abstract
This repo allows you to create a local development cluster using `vagrant` and `ansible`.
<br/>
Solutions like `KinD` and `Minikube` are excellent but often limited.
<br/>
With a cluster made up of several VMs it is possible to test a scenario that is closest to a production context.

## Prerequisites
- `ansible`
- `vagrant`


## Instructions

### Define amount of nodes
Modify the following variable in Vagrantfile:
```
N = <number of worker node here>
```


### Spin up cluster
```
$ vagrant up
```

### Verify on master
```
$ vagrant ssh k8s-master
$ kubectl get nodes
NAME            STATUS   ROLES                  AGE           VERSION
k8s-master      Ready    control-plane,master   5m6s          v1.26.0
k8s-worker-1    Ready    <none>                 2m59s         v1.26.0
k8s-worker-2    Ready    <none>                   68s         v1.26.0
```

## Useful Commands

*vagrant status* — Get the current status of your VM

*vangrant destroy* — Remove all traces of the virtual machine from your system

*vagrant suspend* — Stop the machine and save its current state.

*vagrant provision {vm-name}* — Manually execute ansible playbook against a VM.

*vagrant halt* — Shut down the virtual machine.

*vagrant box list* - List local vagrant box images

*vagrant box remove {vagrant-box-image-name}* - Remove local vagrant box images

*vagrant plugin list* - List local vagrant plugins
