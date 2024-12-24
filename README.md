# Ansible(Configuration Management)

Mantain Multiple servers

1. Ansible using Push Mechanism
2. AgentLess
3. Dynamic Inventory concept
4. It uses yaml file to write the code in Ansible
5. It supports both windows(winRM) and Linux(shh)
6. Ansible support all cloud providers, the only this matter for ansible is
   - Public Ip of the instance
   - SSH access to Ansible
   - Ansible code

### Disadvantages

1. Perfomance
2. Debugging hard to understands
3. Windows user might get into problem

### Diff bt Ansible and Puppet

1. **Puppet**
  * pull Mechanism
  * Master Slave Architecute
  * puppet Language

2. **Ansible**
  * push mechanism
  * Agentless
  * Ansible Playbook(Yaml language)
