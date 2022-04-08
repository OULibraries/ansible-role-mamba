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

While the role should take care of this task for you, the system must have `bzip2` installed for the unarchive module to work.

Role Variables
--------------

There are only two roles variables (found in `defaults/main.yml`). These variables should only need to be updated when switching to a different, newer version of Mamba.

Dependencies
------------

This role does not depend on any other roles. However, this roles should be run against a Linux box that has been recently updated.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
        - OULibraries.mamba

License
-------

[MIT](https://github.com/OULibraries/ansible-role-mamba/blob/master/LICENSE)

Author Information
------------------

James Mitchell
