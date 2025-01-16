## Why Roles

- Roles used to write a complex ansible playbooks to folder like structure..
- Roles gives as readability, modularity and shared accross the world or your organization


# Create a role in ansible

**ansible-galaxy role init test(name of the role)**

- once u executed it will create a folder for you.

# Inside that we have list of folders

- Var : contains variables
- default : we can define default values, if the value is not present in the var folder it will take default value
- task : we can write a collection of task as modules in the folder
- handler : on specific action we can notify the handler e.g. notify the handler to restart the apache server
- files : we can store the files like static html or other files
- templates : ansible used jinja template, here we can files with dynamic content generation
- meta: we can store the meta information like who is the owner and version of the roles...

# how to run the ansible roles

- create an inventory -> create a file called inventory.ini and add the ips
- create a playbook yaml -> create play-book.yaml just mention host and remote user here we need to define the role
- create a role using

    **anisble-galaxy role init test(role name)**

- add the task in task/main.yaml folder in the role
- copy the file to files section
- then come to the playbook
```
    host: all
    remote-user: ubunutu
    roles: 
        - test

```

- then run the command
cmd: **anisble-playbook - inventory.in first-playbook.yml**