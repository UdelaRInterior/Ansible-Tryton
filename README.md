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
      ryton_base_path: /home/tryton
      tryton_python_version: python3
      tryton_python_state: latest
      tryton_postgresql_user: tryton
      tryton_postgresql_pass: tryton
      tryton_postgresql_url: localhost
      tryton_postgresql_port: 5432
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
       tryton_clone_from_repository: true
       tryton_clone_from_url: 'git@github.com:example/project_name.git'
       tryton_clone_dir_name: 'project_name'
```

License
-------

(c) Universidad de la República (UdelaR), Red de Unidades Informáticas de la UdelaR en el Interior. Licenced under GPL-v3.


Author Information
------------------

[@Dkmarce](https://github.com/Dkmarce)  
[@UdelaRInterior](https://github.com/UdelaRInterior)  
https://proyectos.interior.edu.uy/
