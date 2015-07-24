# Ansible playbook stub

В группе http://gitlab.2gis.local/ansible есть роли, которые должны объединяться в playbook'и.
Чтобы применить даже одну роль нужно писать обертку, которая сможет запускаться через `ansible-playbook`.

Этот репозиторий призван немного ускорить этот процесс.

Использовать так:

* В requirements.yml выставляем зависимости на роли
* Скачиваем роли используя `./scripts/fetch-dependencies.sh`
* Редактируем файл hosts, указываем нужные хосты, на которых будет отрабатывать ansible
* Редактируем файл playbook.yml, указывая роли, хосты и нужные доп. переменные

Используем

```sh
$ ansible-playbook -i hosts playbook.yml
```

Если вы используете с sudo, нужно добавить флаг `--ask-sudo-pass`

```sh
$ ansible-playbook -i hosts playbook.yml -vvv --ask-sudo-pass
```

Если возникают сложности, то:
* http://docs.ansible.com/ansible/playbooks.html
* `$ man ansible-playbook`
