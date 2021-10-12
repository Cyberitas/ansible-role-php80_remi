Ansible Role: PHP 80
=========

Ansible role to install PHP version 8.0 on RHEL/CentOS

Requirements
------------

None.

Role Variables
--------------

Additional php extensions are installed when passed in as list items in group_vars and host_vars.
The php_modules_additional takes a list of php extensions to be added in all environments.
```
php_modules_additional:
  - php-pecl-memcache
```

The php_modules-devel variable takes a list of php extensions to be installed in the development environment.
```
php_modules_devel:
  - php-devel
```

Other optional variables include a version number.
```
php_version: "8.0"
```

Dependencies
------------

None.

Example Hosts
----------------
```
ansible.dev.cyberitas.com ansible_connection=local

[lamp]
ansible.dev.cyberitas.com
```

Example Playbook
----------------

```
# play.yml
# ansible-playbook -i hosts play.yml --become
---
- hosts: all
  roles:
    - role: php73remi

# This makes vagrant work for elevated privileges
#   become: yes
#     become_user: "root"
#       become_method: "sudo"
```

License
-------

MIT

Author Information
------------------

Create in 2021 by Tom Emerson for Cyberitas Technologies, LLC
