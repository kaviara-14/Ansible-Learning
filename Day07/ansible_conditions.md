## setup Ansible collection

- Get the Access key and secret key from AWS.
- create the password file
- Create the vault and file add your credentails protect the vault using password file.

- create collection **anisble-galaxy collection install amazon-aws**
- create a yaml file

```
host: localhost
connection: local

tasks:
  - name: Create EC2 instances
    amazon.aws.ec2_instance:
      name: name1
      key_name: "abhi-aws-keypair"
      instance_type: t2.micro
      security_group: default
      region: ap-south-1
      aws_access_key: "{{ec2_access_key}}"  # From vault as defined
      aws_secret_key: "{{ec2_secret_key}}"  # From vault as defined      
      network:
        assign_public_ip: true
      image_id: "{{ item }}"
      tags:
        environment: name1
    loop:
        - ami-129198499300
        - ami-129198499300
        - ami-139950300201
```

- if u see the both ami's are same, anisble are ideompotent in nature..anisble will ignore the 2nd one.to achieve this..

```
host: localhost
connection: local

tasks:
  - name: Create EC2 instances
    amazon.aws.ec2_instance:
      name: "{{item.name}}"
      key_name: "abhi-aws-keypair"
      instance_type: t2.micro
      security_group: default
      region: ap-south-1
      aws_access_key: "{{ec2_access_key}}"  # From vault as defined
      aws_secret_key: "{{ec2_secret_key}}"  # From vault as defined      
      network:
        assign_public_ip: true
      image_id: "{{ item.ami_name }}"
      tags:
        environment: {{item.name}}
    loop:
        - {ami_name: ami-129198499300, name: manage_node1}
        - {ami_name: ami-129198499300, name: manage_node2}
        - {ami_name: ami-139950300201, name: manage_node3}
```

- now if u run: anisble-playbook first-playbook.yml password-file, it will work.

## when command

let say u want to stop the instance 

```
---

host: localhost
connection: local

task
- name: Shutdown ubuntu instances only
      ansible.builtin.command: /sbin/shutdown -t now
        when:
            ansible_facts[os_family] == "debain"