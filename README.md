[![Build Status](https://travis-ci.org/computerlyrik/ansible-awx.svg?branch=master)](https://travis-ci.org/computerlyrik/ansible-awx)

AWX Remote Installer
=========

Installs AWX using the original AWX installer on a remote host.

Supports custom builds of awx_task and awx_web docker-containers.
Built-In Support for python3 runtime environment and builtin debops.

Requirements
------------

Hardware Requirents should match your AWX version.

Role Variables
--------------

The following two variables must be set for this role to work

```
awx__admin_password:
awx__secret_key: 
```

Additionally, `awx__version: ` may be validated.

For everything else see `vars/main.yml` and `defaults/main.yml`


Example Playbook
----------------

```
    - name: install awx
      import_role:
        name: computerlyrik.awx
      vars:
        awx__admin_password: "{{ vault_awx_admin_password }}"
        awx__secret_key: "{{ vault_awx_secret_key }}"
```

License
-------

Apache2

Testing
-------

```
venv virtualenv
source virtualenv/bin/activate
pip install 'molecule[docker]'
molecule test # runs default installation
AWX_VERSION=3.0.1 AWX_DOCKER=true AWX_DOCKER_FLAVOR=debops molecule test # runs customized images installation
```

TODO
----

* Verify, that python3-variant works

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
