## Run play book

```
  ansible-playbook -i dev.inv apache.yml
```

### Passing variables to playbook at command line

```
  ansible-playbook -e apache_port=90 -i dev.inv apache.yml
```
