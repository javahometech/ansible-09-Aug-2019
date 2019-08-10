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

### Ansible Vault
Ansible vault is used for encrypting sensitive data in ansible.

#### Encrypt Variables using vault

```
  ansible-vault encrypt vars.yml
  
```

#### Vault ask password at command line

```
  ansible-playbook -i dev.inv vault-demo.yml --ask-vault-pass
```

#### Vault password from a file

```
  ansible-playbook -i dev.inv vault-demo.yml --vault-password-file=~/vault.txt
  
```

#### Vault password using environment variable
```
  export ANSIBLE_VAULT_PASSWORD_FILE=~/vault.txt
  ansible-playbook -i dev.inv vault-demo.yml
  
```

#### Editing encrypted variables file
```
  ansible-vault edit vars.yml
  
```

#### Decrypting variables file
```
  ansible-vault decrypt vars.yml
  
```

#### Encrypting only specific values in variables file
```
  ansible-vault encrypt_string  'Admin@!@#$' --name 'db_password'
  
```

