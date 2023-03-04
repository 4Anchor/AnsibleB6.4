# Ansible repository

## Роли

### Postfix

Используется если надо установить Posfix

```
ansible-playbook -i inventory/sf_postfix.yml --skip-tags=drop playbooks/playbook-all.yml --check
```


### Postfix Drop

Используется если надо удалить Postfix

```
ansible-playbook -i inventory/sf_postfix.yml --tags=drop playbooks/playbook-all.yml -v 
```

### vsftpd

Используется если надо установить vsftpd

```
ansible-playbook -i inventory/sf_hwork.yml --tags=deploy_vsftpd playbooks/playbook-all.yml -v
```

### Docker

Используется если надо установить docker

```
ansible-playbook -i inventory/localhost.yml playbooks/playbook_h.yml -v
```