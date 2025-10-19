![Ansible Lint](https://github.com/johanneskastl/ansible-role-doas_configuration/workflows/Ansible%20Lint/badge.svg)

doas_configuration
=========

Configure doas.

Requirements
------------

None.

Role Variables
--------------

- `doas_user_or_group` (string): Name of the user or group that should be added
  to the doas configuration. By default, this uses the `ansible_user`.
  If you want to use a group, be sure to prefix it with a colon, e.g. `:wheel`.
- `doas_configuration_additional_rules` (list of dicts): additional doas rules
  that should be created. The information in each list contains:
  - `name` (string): used for the file name
  - `command` (string): filename or full path to the command to be executed
  - `arguments` (string): if defined, those are added as arguments to the rule.
    If this is unset, the rule makes sure the command is called without
    arguments
  - `allow_nopass` (Boolean): Whether or not to inclde the `nopass` option


Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: johanneskastl.doas_configuration

Example Playbook with an additional rule
----------------

    - hosts: servers
      roles:
        - role: johanneskastl.doas_configuration
          vars:
            doas_configuration_additional_rules:
              - name: RESTART_NAMED
                command: /sbin/rc-service
                arguments: named restart
                allow_nopass: true

License
-------

BSD-3-Clause

Author Information
------------------

I am Johannes Kastl, reachable via git@johannes-kastl.de.
