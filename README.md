# ansible_tutorial
Ansible ssh git

```vi .ssh/config```

```
Host github_ssh_connection
   HostName github.com
   IdentityFile ~/.ssh/28-31-ansible
``` 

```git clone git@github_ssh_connection:rsolovyeaws/ansible_tutorial.git```

Add inventory file with IP adresses 

Run ad-hoc ping command 

```ansible all --key-file ~/.ssh/28-31-ansible -i inventory -m ping```
