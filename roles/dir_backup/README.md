Role Name
=========

Role for backup directory in S3 bucket.

Requirements
------------

None

Role Variables
--------------

**PROJECT:** 
>Project name. Example: "project-1"

**ENVIRONMENT:** 
>Environment. Example: "dev"

**TARGET_DIR:** 
>Target directory for backup. Example: "/usr"

**BACKUP_DIR:** 
>Directory for mount endpoint s3 bucket. Example: "backup_s3/"

**BACKUP_FILE_NAME:** 
>Filename for tarball. Example: "jira-home"

**BACKUP_BUCKET_NAME:** 
>S3 bucket name. Example: "test-infra-buckup"

**BUCKET_KEY_ID:** 
>SA access key id for upload tarball in S3 bucket.

**BUCKET_ACCESS_KEY:** 
>SA secret key id for upload file in S3 bucket.

**BUCKET_PATH_PREFIX:** 
>Path for upload tarball in S3 bucket

**BACKET_URL:** 
>URL for connect in S3 service "https://HOST_NAME/"

Dependencies
------------

None

Example Playbook
----------------

    - name: backup data directory
      include_role:
        name: dir_backup
      vars:
        TARGET_DIR: "/var/atlassian"
        BACKUP_FILE_NAME: "confluence-var"