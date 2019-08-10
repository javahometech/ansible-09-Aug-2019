## Run play book

```
  ansible-playbook -i dev.inv apache.yml
```

### Passing variables to playbook at command line

```
  ansible-playbook -e apache_port=90 -i dev.inv apache.yml
```

### Ansible Facts
Ansible gathers facts of every Node using setup module

```
ansible all -m setup -a  'filter=*cpu*'

```
