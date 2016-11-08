ndobbs.ansible-role-zoneminder
=========

Installs & configures ZoneMinder on EL.

Requirements
------------

None

Role Variables
--------------

```yaml
# Passwords required for installation
mysql_root_pwd: "root"

# Zoneminder db credentials
zm_db_user: "zmuser"
zm_db_user_password: "zmpass"

# zmrepo variables
# currently only supports EL6.x OS'
#   * RHEL 6.x
#   * CentOS 6.x
 
# zmrepo install URL
zmrepo_url_el6: "http://zmrepo.connortechnology.com/el/{{ ansible_distribution_major_version }}/{{ ansible_architecture }}"

# Timezone information
# A proper install requires /etc/php.ini configuration
# This role will assume you are gathering facts and will set date.timezone based upon machine configuration
date_timezone: "{{ ansible_date_time.tz }}"
```

Dependencies
------------

```yaml
# .requirements.yml
- name: ansible-role-apache
  src: geerlingguy.apache
- name: ansible-role-mysql
  src: geerlingguy.mysql
- name: ansible-role-php
  src: geerlingguy.php
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - name: "Ensure Apache httpd"
      role: ansible-role-apache
    - name: "Ensure MySQL"
      role: ansible-role-mysql
    - name: "Ensure PHP"
      role: ansible-role-php
    - name: "Ensure ZoneMinder"
      role: ndobbs.ansible-role-zoneminder
```

License
-------
BSD

TODO
------------------
Add SSL configuration support
Add support for RHEL 7
Add support for debian distros

Author Information
------------------

This Ansible role was created by Nate Dobbs in 2014.
