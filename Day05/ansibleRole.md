## Install existing Ansible Roless

- Go to the Ansible Galaxy it's a market place for Ansible roles
- let say u want to install docker for redhat, debain and windows machine, in the ansible galaxy search for the respective roles
- copy the command and come to the cli
- **ansible-galaxy role install deb-docker(role name)**
- once u done it will installed in this path */ansible/role*
- now here create a inventory and enable password less authentication for remote servers.
- write a yaml file 

```
    host: all
    remote-user: root
    roles:
        - deb-docker
```

- save it.
- run the command called **ansible-playbook -i inventory.ini playbook-name**

## How to import Ansible roless..

- This we already have a role in the local.
- first create repo..
- initalize the repo
- git remote add origin <git url>
- git add .
- git commit -m "intialize file"
- git push origin master
- our role will be published to the git repo..
- now we need to use ansible-galaxy import <github-username> <github-reponame>