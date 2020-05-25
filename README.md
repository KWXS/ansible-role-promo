keller.promo
=========

Ansible role for install promo project.

  - keller_promo

Ste-by-step
------------

  - Setup Kellermanagement docker containers project and pull images from https://github.com/KWXS/km-containers
  - Download needed ansible roles
  - Create ansible playbook and fill role variables
  - Setup awscli with keys for pulling images from AWS ECR
  - Add public ssh-key in guthub account for pull repository via ansible role
  - Run ansible playbook

Requirements
------------

```git
php@7.4
mysql@5.7
redis-server
nginx
docker
docker-compose
awscli aws-cli/1.16.248 version (pip install awscli==1.16.248)
```

awscli must be installed and configured, AWS keys have permission to pulling images from AWS ECR.
Public ssh-key must be added on github account (https://github.com/settings/keys)

Role Variables
--------------

ansible_user: "user" os username
work_dir: "work"
promo_git:
promo_git_branch:
promo_dir:
work_domain:
database:
app_key:
minio_key:
minio_secret:
app_env:

Dependencies
------------

  - homebrew
  - python@3
  - ansible

Example Playbook
----------------

    - hosts: localhost
      become: no
      vars:
        ansible_user: "user"
        work_dir: "work"
        promo_git:
        promo_git_branch:
        promo_dir:
        work_domain:
        database:
        app_key:
        minio_key:
        minio_secret:
        app_env:
      roles:
        - keller.promo

License
-------

BSD

Author Information
------------------

KWXS
