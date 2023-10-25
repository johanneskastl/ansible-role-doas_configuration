![Ansible Lint](https://github.com/johanneskastl/ansible-role-doas_configuration/workflows/Ansible%20Lint/badge.svg)

doas_configuration
=========

Configure doas.

Requirements
------------

None.

Role Variables
--------------

- `doas_user` (string): Name of the user that should be added to the doas
  configuration. By default, this uses the `ansible_user`.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: 'johanneskastl.doas_configuration'

License
-------

BSD-3-Clause

Author Information
------------------

I am Johannes Kastl, reachable via kastl@b1-systems.de.
