OULibraries.mamba
=========

This Ansible role utilizes [the Mamba project](https://mamba.readthedocs.io/en/latest/) to bypass and protect the system Python on OU Libraries infrastructure. This role allows individuals to run multiple, newer versions of Python on OU Libraries instances without modifying the system Python or altering it in any way. This role can also be used to isolate dependencies between user and project on the same machine.

This role:

 - installs micromamba
 - makes the binary available for execution
 - creates a micromamba user where environments can be created
 - adds some environment variables that can be set is desired
 

 This role does NOT:
 
 - initialize a base environment
 - create any environments
 - install any dependencies required by an environment

Any additional functionaly will need to be handled by another playbook or by running additional roles.

Requirements
------------

This roles assumes you are running it against a CentOS 7 machine.

Role Variables
--------------

There are only two roles variables (found in `defaults/main.yml`). These variables should only need to be updated when switching to a different, newer version of Mamba.

Dependencies
------------

- `bzip2`

Example Playbook
----------------

To explicitly run this role in a playbook or role, add the following:

    - hosts: all
      roles:
        - OULibraries.mamba

You can also add the role as a dependency in another role. For example, add the following to your `meta/main.yml` file:

    dependencies:
      - role: OULibraries.mamba

This inclusion will ensure the mamba role is run before the role on which it depends.

License
-------

[MIT](https://github.com/OULibraries/ansible-role-mamba/blob/master/LICENSE)

Author Information
------------------

James Mitchell
