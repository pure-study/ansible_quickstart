# ansible_quickstart

Practices of this guide: [Getting started with Ansible](https://docs.ansible.com/ansible/latest/getting_started/index.html).

Preparation:
```shell
# Prepare an container on local before testing Ansible
cd test-container
nerdctl build -t ssh_server .
nerdctl run -d -p 2222:22 --name ssh_container ssh_server
ssh sshuser@localhost -p 2222
ssh-copy-id -i ~/.ssh/id_rsa.pub -p 2222 sshuser@localhost
```

Relevant commands of this repository:
```shell
ansible-inventory -i inventory.ini --list
ansible myhosts -m ping -i inventory.ini -u sshuser

```