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

Add ansible.cfg with contents:
[defaults]
inventory = inventory
private_key_file = ~/.ssh/28-31-ansible

#invetory - points to invetory file with hosts
#private_key_file - points to ssh private key for hosts

ansible.cfg in the repository will override /etc/ansible/ansible.cfg 
and will shorttent previous ad-hoc command to:
```ansible all -m ping```

---other usefull comands:
```
ansible all --list-hosts
ansible all -m gather_facts
ansible all -m yum -a update_cache=true --become --ask-become-pass
```

fininshed tutorial: 
NOTES: IP's in the inventory file and host_vars are local VM's.
FAILS->SOLUTIONS: ansible could not parse sshd_config_file variable from the host_vars, had to make two plays distinguished by asnsible distriution variable
