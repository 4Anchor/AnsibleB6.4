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
### Playbook добавления пользователя

Используется для до добавления пользователя с правами sudo на удаленный хост.

```
ansible-playbook --vault-password-file=/opt/vault-pass -i inventory/sf_hwork.yml playbooks/add_user.yml -v
```

### Playbook добавления пользователей и группы

Используется для до добавления нескольких пользователей и группы "Superuser" с правами sudo на удаленный хост.

```
ansible-playbook playbooks/superuser.yml -i inventory/sf_hwork.yml --vault-password-file=/opt/vault-pass -v
```
### Playbook установки dnsmasq и nginx+php-fpm

Используется для установки на хост сервиса dnsmasq и nginx+php-fpm адрес страницы для проверки /info.php
```
ansible-playbook -i inventory/sf_hwork.yml --tags=deploy_nginx playbooks/playbook-all.yml -v
```
