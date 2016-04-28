Dumpall
========

Dump all ansible variables into a file on localhost
Based on the excellent work by [Lester Wade](https://coderwall.com/p/13lh6w)!

NOTE: extra-vars, role-vars and a few other hidden variable sets are not yet included.

Requirements
------------

None.

Role Variables
--------------

    dumpall_flat_mode: yes
    dumpall_localhost_destination: /tmp/ansible_vars.json

Example Playbook
-------------------------

Example with a host_destination will result in a dumpfile /examine/ansible.all on the localhost machine:

    - hosts: servers
      tasks & roles ...

    - hosts: localhost
      roles:
         - { role: ansible-dumpall, dumpall_localhost_destination: /examine/ansible.all }

License
-------

LGPL

Author Information
------------------

Jasper N. Brouwer, jasper@nerdsweide.nl

Ramon de la Fuente, ramon@delafuente.nl

Larry Fast, lfast1960 at yahoo dot com
