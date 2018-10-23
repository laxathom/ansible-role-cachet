Ansible-role-cachet
===================

Ansible role to install and configura cachet status page on RHEL/CentOS (for now).


Role Variables
--------------

These are settable variables for this role and are pre-defined into `defaults/main.yml` with default values.
You might need to override them according to your need. Most of them **are not suitable** for a production environment.


Highlight variables
```yaml
cachet_install_php:     # Install pre-defined php role as dependency if set to True
cachet_install_mysql:   # Install pre-defined mysql role as dependency if set to True
cachet_install_pgsql:   # Install pre-defined pgsql role as dependency if set to True

cachet_install_dir:     # Defines application installation directory
cachet_branch_version:  # Defines application version to install
```

Dependencies
------------

* geerlingguy.repo-remi
When variable `cachet_install_php` is true.

* geerlingguy.php
when variable `cachet_install_php` is true.

* geerlingguy.mysql
When variable `cachet_install_mysql` is true.

* geerlingguy.mysql
When variable `cachet_install_pgsql` is true.

Note that if you manage to use different roles than those above (or db servers are installed elsewhere), consider setting those variables to `False` and make sure to run and deploy them first.


Example Playbook
----------------

```yaml
    - hosts: status-servers
      roles:
         - laxathom.cachet
```
