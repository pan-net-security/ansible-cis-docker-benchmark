ansible-cis-docker-benchmark
=========

This role applies the Docker CIS Benchmark 1.2 - sections 1, 2 and 3.

Requirements
------------

- Docker engine
- Ansible >= 2.8

Role Variables
--------------

`cdb_config_file (default: /etc/docker/daemon.json)`
This variable is path to the Docker daemon configuration file. During execution this role assumes the config file defined here should be changed according to the defined security practices.

`cdb_config_file_create (default: false)`
This variable will trigger config file creation if it already doesn't exist.

`cdb_dockerd_via_network (default: false)`
This variable will trigger configuration changes related to exposing Docker via TCP over network.

`cdb_default_ulimits_nofile_soft (default: 100)`
This variable sets soft limit for number of opened files.

`cdb_default_ulimits_nofile_hard (default: 200)`
This variable sets hard limit for number of opened files.

`cdb_default_ulimits_nproc_soft (default: 1024)`
This variable sets soft limit for maximum number of processes for all containers.

`cdb_default_ulimits_nproc_hard (default: 2048)`
This variable sets hard limit for maximum number of processes for all containers.

`cdb_syslog_address (default: '')`
This variable defines remote syslog for storing log files.
Default value should be changed to point to remote syslog server.

`cdb_seccomp_profile (default: '')`
This variable hold path to the seccomp profile.
If left empty, Docker daemon will use default seccomp profile.

`cdb_authorization_plugins (default [])`
The list of authorization plugins.
This variable must be set in order to comply with CIS Benchmark.
https://docs.docker.com/engine/extend/plugins_authorization/


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
virtualenv -p python3 .venv
. .venv/bin/activate
pip install molecule[docker] molecule[vagrant] python-vagrant docker
molecule test
# or [currently broken]
molecule test -s docker-ubuntu
````

TODO
-----

The following requirements are not checked, because:

* Docker Registry is not being checked: 3.7, 3.8


License
-------

BSD

Author Information
------------------

Diogenes Santos de Jesus
Miroslav Bagľaš
