Role Name
=========
ndobbs.ansible-role-zoneminder

Requirements
------------

If you are not familiar with ansible or not using a 'role' file structure: ( http://docs.ansible.com/playbooks_best_practices.html#directory-layout )

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

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
