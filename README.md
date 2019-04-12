Role ansible-pip
=========

Requirements
------------

N/A

Role Variables
--------------
Python packages required to use pip 

```
pip_package: python-pip 
```

The epel-release repository. 
TO-DO Still working for other release like 6 and 5.

```
pip_epel_release: 7
```
Defines the python packages to install using the ansible pip module

```
pip_install_packages: []
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: servers
  roles:
      - { role: robedevops.pip }
```

License
-------

BSD

Author Information
------------------

Roberto Cardenas Isla - email: rcardenas20@gmail.com