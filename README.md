Ansible - Tryton
=========

Role that install dependencies for tryton and clone from a repository if neccesary.

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
          tryton_user: tryton
          tryton_pass: tryton 
          tryton_port: 8080
          tryton_base_path: /home/tryton
          python_version: python3
          python_state: latest
          postgresql_url: localhost
          postgresql_port: 5432
          tryton_pip_packages: 
            - trytond>=4.6,<4.7
            - bcrypt
            - psycopg2
            - trytond_company>=4.6,<4.7
            - trytond_currency>=4.6,<4.7
            - trytond_party>=4.6,<4.7
            - trytond_stock>=4.6,<4.7
            - trytond_product>=4.6,<4.7
            - trytond_ldap_authentication>=4.6,<4.7
            - py-xlsx
            - pytz
            - fuzzywuzzy    
          tryton_email_uri: "smtp://example.com:25"
          tryton_authentications: "ldap,password"

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
```

License
-------

(c) Universidad de la República (UdelaR), Red de Unidades Informáticas de la UdelaR en el Interior. Licenced under GPL-v3.


Author Information
------------------

[@Dkmarce](https://github.com/Dkmarce)  
[@UdelaRInterior](https://github.com/UdelaRInterior)  
https://proyectos.interior.edu.uy/
