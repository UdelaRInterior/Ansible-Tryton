Ansible - Tryton
=========

Role to install tryton and dependencies inside a python environment and clone a tryton module repository if necessary.

This role also allows you to install the `sao` client.

Requirements
------------

Ansible version >= 2.7

Example Playbook
------------

```yaml
- hosts: servers
  roles:
    - role: udelarinterior.Ansible-Tryton
      tryton_versions:
        tryton_dev:
          user: tryton
          pass: tryton 
          pass_salt: s3cr3t
          shell: /bin/bash
          base_path: /home/tryton          
          port: 8080
          python_version: python2.7
          python_state: latest
          python_virtualenv_path: python
          python_virtualenv_command: false
          debian_packages_install:
            - python
            - python-dev
            - gcc
            - libpq-dev
            - virtualenv
          pip_packages_update:
            - pip
            - virtualenv
          pip_tryton_packages: 
            - trytond>=4.6,<4.7
            - bcrypt
            - psycopg2-binary   
          email_uri: "smtp://example.com:25"
          authentications: "ldap,password"
          postgresql_url: localhost
          postgresql_port: 5432
          postgresql_user: tryton
          postgresql_pass: tryton
    
          ##GIT CLONE
          clone_from_repository: true
          clone_from_url: ''
          clone_dir_name: ''
          clone_git_url: gitlab.com
          clone_is_private: true
          clone_deploy_key: "deploy_key"
          
          ##REPO SYM LINK
          clone_sym_link_module: "request"
          
          ##LDAP
          ldap_bind_pass: "password"
          ldap_uid: "uid"
          ldap_uri: "ldap://ldap.example.com/ou=group,dc=example,dc=com??subtree??bindname=cn=login,cn=example,ou=group,dc=example,dc=com"
          
          ##SAO
          sao_install: true
          sao_nodejs_version: "12.x"
          sao_version: "4.6.0"
          sao_dest: "/srv"

          #optional
          #systemd_service: service_name
          #systemd_description:
          #systemd_start:
          #systemd_stop:
          #systemd_enviroment:
            #- name:
            #  value:
```


License
-------

(c) Universidad de la República (UdelaR), Red de Unidades Informáticas de la UdelaR en el Interior. Licenced under GPL-v3.


Author Information
------------------

[@Dkmarce](https://github.com/Dkmarce)  
[@andrespias](https://github.com/andrespias)
[@UdelaRInterior](https://github.com/UdelaRInterior)  
https://proyectos.interior.edu.uy/
