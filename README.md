mario_slowinski.service
=========

Install and allow in firewall systemctl service.

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)
* [ansible.posix](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html)

Role Variables
--------------

* defaults

  ```yaml
  service_pkgs: []      # list of packages required by the service
  - name: []            # list of packages names to install

  service_firewalld:    # firewalld settings
    zones: []           # list of firewalld zones
      - name:
        services: []     # list of services to allow in firewalld
        ports: []       # list of ports to allow in firewalld
  ```

Dependencies
------------

* [mario_slowinski.software](https://galaxy.ansible.com/mario_slowinski/software)

Example Playbook
----------------

* playbook usage

  ```yaml
  - hosts: servers
    gather_facts: yes  # to determine ansible_os_family
    roles:
    - role: mario_slowinski.service
  ```

* role dependency usage

  ```yaml
  - dependencies:
    roles:
    - role: mario_slowinski.service
      service_pkgs: "{{ role_pkgs }}"
      service_firewalld: "{{ role_firewalld }}"
  ```

License
-------

[GPL-2.0-or-later](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)
