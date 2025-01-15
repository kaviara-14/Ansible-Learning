1. Before Ansible, people if they want to install any software or upgrades the os on the VM.they will login to each and every application and do the necessity function.for every os they have different commands.

After,
    1. Puppet
    2. Chef
    3. Ansible came..

## Puppet and Chef

- for pupet and chef, we need to install the pupet or chef software on all the vm, so that it will work(not agentless)
- for pupet and chef, they have their respective programming languages..we need to learn..learning those things makes somet times things complex.

## Ansible

- Ansible is Agentless.
- only prerequsites we need to install python all the machine.
- Here we have control node and manage node.
- u can choose any os distribution as control node in VM, install ansible and create inventory and run the command..it will install necessary software in all the manage nodes. 
- In the inventory we need to add the public ip of the other vm's(manage node).

- Ansible we need to write it in YAML File, this will convert the yaml code to python..and with python it will communicate automatically to other vm's.


## Installing a software

## 1. Why not Shell scripting ?

- shell scripting only supports for linux for windows it will not work.

## 2. Python

- python is a one of choice, but we need to update the package every time
- need some complex code.

## 3. Ansible

- Ansible is the right option.