########## Роль настроийки пользователей и БД в PostgreSQL

Роль итерируемая, цикл описан в плэйбуке, смысл в том, чтобы забирать cred's из Vault по каждому значению переменной microservice

Для ее использования, необходимо заполнить kv в Vault по пути {{project}}/{{env}}/{{microservice}}/postgresql следующие переменные (json from Vault):

{
  "db_name": "new-db",        ###  название БД
  "user_name": "user-test",   ###  имя пользователя
  "user_pass": "test1234"     ###  пароль пользователя
}

Далее указываем для каких микросервисов настраиваем БД:

microservice: [microservice1, microservice2] 

#Обязательные переменные:

project: tms #Укажите название проекта
env: dev #Укажите окружение
vault_token: #Укажите свой vault token

#Опциональные переменные

vault_mountpoint: project_secrets
vault_url: https://pki.HOST_NAME.ru/
vault_secret: ###ОПЦИОНАЛЬНЫЙ ПАРАМЕТР#####Укажите mount_point секретов БД, 
              ###по-умолчанию значение вычисляемое: {{project}}/{{env}}/{{microservice}}/postgresql
ACTION: "init_db"

Переменная user_db_privileges: - задает права на БД для пользователей см. https://docs.ansible.com/ansible/latest/collections/community/postgresql/postgresql_user_module.html