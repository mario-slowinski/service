service
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

* [software](https://galaxy.ansible.com/mario_slowinski/software)

Example Playbook
----------------

* `requirements.yml`

  ```yaml
  - name: service
    src: mario_slowinski.service
  ```

* playbook usage

  ```yaml
  - hosts: servers
    gather_facts: yes  # to determine ansible_os_family
    roles:
      - role: service
  ```

* role dependency usage

  ```yaml
  - dependencies:
      - name: service
        src: mario_slowinski.service
        service_pkgs: "{{ role_pkgs }}"
        service_firewalld: "{{ role_firewalld }}"
  ```

License
-------

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)
