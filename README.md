Dumpall
========

Dump all remote variables and optionally copy the result to a destination on the host.

Based on the excellent work by [Lester Wade](https://coderwall.com/p/13lh6w)!

Requirements
------------

Debian Wheezy or RedHat 6 with the package python-pycurl and python-software-properties installed.

Role Variables
--------------

    dumpall_flat_mode: yes
    dumpall_guest_destination: /tmp/ansible.all
    dumpall_host_destination: /somewhere/local/

Example Playbook
-------------------------

Example without a host_destination will result in a dumpfile /tmp/ansible.all on the guest:

    - hosts: servers
      roles:
         - f500.dumpall

Example with a host_destination will result in a dumpfile /examine/ansible.all on the host machine:
(the dumpfile on the guest is removed)

    - hosts: servers
      roles:
         - { role: f500.dumpall, dumpall_host_destination: /examine/ }

If you also set the flat_mode to false, the local filename will be the entire path of the guest_destination,
prepended by the hostname of the current play. See the Ansible _fetch_ module for more information.

License
-------

LGPL

Author Information
------------------

Jasper N. Brouwer, jasper@nerdsweide.nl

Ramon de la Fuente, ramon@delafuente.nl
