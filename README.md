ndobbs.ansible-role-zoneminder
=========

Installs & configures ZoneMinder on EL.

Requirements
------------

None

Role Variables
--------------

```yaml
# ansible-role-zoneminder/defaults/main.yml
# ---
# Zoneminder db credentials
zm_db_root_password: "root"
zm_db_user: "zmuser"
zm_db_user_password: "zmpass"

# zmrepo install URL
zm_yum_repo_url: "http://zmrepo.zoneminder.com/el/{{ ansible_distribution_major_version }}/{{ ansible_architecture }}"

# Timezone information
# A proper install requires /etc/php.ini configuration
# This role will assume you are gathering facts and will set date.timezone based upon machine configuration
date_timezone: "{{ ansible_date_time.tz }}"


# ansible-role-zoneminder/vars/main.yml
# ---
# Create maps of options that differ by EL version
zm_db_options: 
  6: "mysqld"
  7: "mariadb"
zm_path_conf_options:
  6: "/etc/zm.conf"
  7: "/etc/zm/zm.conf"

# Populate values from options maps
zm_db: "{{ zm_db_options[ansible_distribution_major_version] }}"
zm_path_conf: "{{ zm_path_conf_options[ansible_distribution_major_version] }}"
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - name: "Ensure ZoneMinder"
      role: ndobbs.ansible-role-zoneminder
```

License
-------
BSD

TODO
------------------
Add SSL configuration support
Add support for debian distros

Author Information
------------------

This Ansible role was created by Nate Dobbs in 2014.
