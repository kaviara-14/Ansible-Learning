## Anisble Collection

- using Ansible collection we can create infrastructure in third party tools like aws, azure and so on.
- for that we need to install collection from the ansible-galaxy documentation.
- let say i want to create aws ec2 instance
- go to the collections in ansible galaxy in the go to aws install the collection for aws.
- copy the command. **anisble-galaxy collection install aws-amaxon**.
- install python
- why ? in the control node ansible will  install all the modulues. using python it talks to the thirdparty api server and create the infrastrcure.
- create a yaml file

```
host : localhost
network : local
roles:
    - ec2
```
- create a role called ec2 and got to the task/main.yaml and add code from the ansible-galaxy for ec2-instance.
- for storing secretes we will use Ansible vault
- we will create a password.
- will encrypt the vault file using password, in vault file add the secrets like secret key and access token of aws.
- finally run that using 

- **ansible-playbook -i inventory playbook.yml and pass the vault file also also**


## Variables

- Variables will have precendence(top most is priority) which means it will over-riden we can use variables in 22 places in ansible.
- one way we can  use variables in default folder and pass the name of the variable in the yaml file "{{type}}".
- defulat folder will be over ridden easily by var folder variables..var is having high priortiy than default..
- ansible will automatically fetchs the variables from the var or default folder..
- most powerful variable which cannot be overriden by anyone is extravars, we can give this in command line
**ansible-playbook -i inventory.yml playbook.yml -e type:t2.micro**
- another one is group vars we can groupby the variables based on the task or yaml file.
- another one we can give variable inside the yaml file also seperate var for seperate task.