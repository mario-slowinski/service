service
=======

Install and allow in firewall systemctl service.

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)
* [ansible.posix](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html)

Role Variables
--------------

* defaults

  ```yaml
  service_name: ""      # name of systemd service to start/enable

  service_pkgs: []      # list of packages required by the service
  - name: []            # list of packages names to install

  service_firewalld:    # firewalld settings
    zones: []           # list of firewalld zones
      - name:
        services: []    # list of services to allow in firewalld
        ports: []       # list of ports to allow in firewalld
  ```

Dependencies
------------

* [software](https://galaxy.ansible.com/mario_slowinski/software)

Tags
----

* service.firewall
* service.state

Example Playbook
----------------

* `requirements.yml`

  ```yaml
  - name: service
    src: https://github.com/mario-slowinski/service
  ```

* playbook usage

  ```yaml
  - hosts: servers
    gather_facts: yes  # to determine ansible_os_family
    roles:
      - role: service
  ```

License
-------

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)
