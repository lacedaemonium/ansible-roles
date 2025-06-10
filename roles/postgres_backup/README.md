##########Обновленная роль бэкапа PostgreSQL#

Роль создает дампы в формате .gz

Обязательные переменные для заполнения:
BACKUP_BUCKET_NAME: #Имя бакета, пример: tms-backups
BUCKET_KEY_ID: 
BUCKET_ACCESS_KEY:
DATABASES: # Список баз данных пример:[test, test2]
PROJECT: #Проект
ENVIRONMENT: #Окружение dev,qa,prod


##########Опциональные переменные:
BUCKET_PATH_PREFIX: # Имя папки с дампами, по-умолчанию: "psql_backups"
REMOVE_OLD_FILES: true
RETENTION_DAYS: 30d
