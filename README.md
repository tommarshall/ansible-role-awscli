Ansible Role: AWS CLI
=========

[![Build Status](https://travis-ci.org/tommarshall/ansible-role-awscli.svg?branch=master)](https://travis-ci.org/tommarshall/ansible-role-awscli)

Installs [AWS Command Line Interface](https://aws.amazon.com/cli/) on RHEL/CentOS or Debian/Ubuntu servers via `pip`. Configures AWS CLI user credentials, including support for profiles.

Requirements
------------

None.

Role Variables
--------------

```yml
# Name of the 'pip' package to install
awscli_pip_package: python-pip

# Version of 'awscli' to install
awscli_version: 1.11.73
```

```yml
awscli_users: []

# Example:
#
# awscli_users:
#   - username: joebloggs
#     access_key_id: AKIAIOSFODNN7EXAMPLE
#     secret_access_key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
#     region: eu-west-1
#     output: text
#   - username: janebloggs
#     profiles:
#       - name: default
#         access_key_id: AKIAIOSFODNN7EXAMPLE
#         secret_access_key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
#         region: eu-west-1
#         output: text
#       - name: foo-profile
#         access_key_id: AKIAIOSFODNN7EXAMPLE
#         secret_access_key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
#         region: us-east-1
#         output: json
```
The users' AWS config and credentials. `profiles` is optional, but takes precedence if set, i.e. the `default` profile must be defined within `profiles`, if required.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: tommarshall.awscli }

License
-------

MIT / BSD
