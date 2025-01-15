## Password Less Authentication

we can achieve this using 2 ways

 - use pem file
 - enable password less Authentication as yes and create password

use pem file

 - ssh copy id we can use 

passwordless Authentication

 - we can got /etc/cloud_config
 - changes the password less authenication to yes
 - create a password


## Inventory

- we can create Inventory using vim inventory.ini or by default the ansible will take this path /etc/ansible/host as inventory
- once we created inventory file, we need to add the username with public ip of the instance.
- we can add like this ubuntu@12.123.313.11
- we can also groupby this using, 
[api]
ubuntu@129.13.1.3
ubuntu@90.23.1.2

[db]
ubuntu@34.43.12.5

- once it is done for running the inventory file
- we can use **ansible -i inventory.ini -m ping all** - this will take all ip (or)
- we can use **ansible -i inventory.ini -m ping ubuntu@123.33.14.1** - this will take specific ip (or)
- we can use **ansible -i inventory.ini -m ping db** - this will run for the particular group (or)

- in the inventory, we have something called this -m which means module(shell like that etc)
- in the inventory, we also have this called -a arguments we can pass arguments(to those)

- **inventory -i inventory.ini -m shell -a "ls" all**
- with the password less authentication enabled ansible connect to all the instance