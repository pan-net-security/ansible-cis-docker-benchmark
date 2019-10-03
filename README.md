ansible-cis-docker-benchmark
=========

This role applies the Docker CIS Benchmark 1.2 - sections 1, 2 and 3.

Requirements
------------

- Docker engine
- Ansible >= 2.8

Role Variables
--------------

:TODO

Dependencies
------------

:TODO

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


```
    - hosts: servers
      roles:
        - { role: ansible-cis-docker-benchmark }

```

Development
-----------

```
virtualenv -p python3 venv
. venv/bin/activate
pip install molecule[docker]
molecule test
````

License
-------

BSD

Author Information
------------------

Diogenes Santos de Jesus
Miroslav Bagľaš
