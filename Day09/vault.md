## Ansible Vault

1. we need to create a password.
2. Then we need to encrpyt the file or string using the password in Ansible Vault

commands:

**anisble-vault create credenitals.yml -vault-password value.pass**

- we can create a ansible vault, inside we can create a file..store the credntails encrypt using password 

**ansuble-vault encrpty** -- if u already have file u need to encrypt
**ansible-vault view** -- to view the encrpyted data
**anisble-vault edit** -- to edit the exisiting encrypted data
**ansible-vault encrpyt-string** -- to encrypt the string using password