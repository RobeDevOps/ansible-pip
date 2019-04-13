Role ansible_pip
=========

Requirements
------------
Ubuntu requires the python-apt package installed on remote hosts.

Role Variables
--------------
Python packages required to use pip 

```
# Centos 
pip_package: python36-pip

# Debian | Ubuntu
pip_package: python3-pip
```

Defines the packages to install using the ansible pip module
```
pip_install_packages: []
```

Example Playbook for CentOS | RedHat
----------------

Using variables.

```
- hosts: servers
  vars:
    pip_package: python36-pip
    pip_install_packages:
      - docker
  roles:
      - { role: robedevops.ansible_pip }
```

Example Playbook for Ubuntu 18.04 
----------------

Using python3-pip need to specify also the python interpreter to avoid this issue:

```
fatal: [servers]: FAILED! => {"changed": false, "msg": "No setuptools found in remote host, please install it first."}
```

Playbook definition with python3-pip

```
- hosts: servers
  vars:
    ansible_python_interpreter: /usr/bin/python3
    pip_package: python3-pip
    pip_install_packages:
      - docker

  roles:
      - { role: robedevops.ansible_pip }
```

License
-------

BSD

Author Information
------------------

Roberto Cardenas Isla - email: rcardenas20@gmail.com