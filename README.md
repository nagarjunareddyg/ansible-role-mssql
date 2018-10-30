mssql
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-mssql.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-mssql)

Provides Microsoft SQL Server for your system.


Example Playbook
----------------

This example is taken from `molecule/default/playbook.yml`:
```
---
- name: Converge
  hosts: all
  gather_facts: false

  roles:
    - robertdebock.bootstrap
    - robertdebock.mssql

```

Role Variables
--------------

These variables are set in `defaults/main.yml`:
```
---
# defaults file for mssql

# mssql_add_repositories can be used to select if you want the repositories installed by this role.
# See vars/main.yml for the location of the repositories. Can be: yes, true or 1.
mssql_add_repositories: yes

# mssql_sa_password contains the password for a system administrator.
# The password must be at least 8 characters long and contain characters from three of the following four sets:
# - uppercase letters
# - lowercase letters
# - numbers
# - and symbols
mssql_sa_password: "StR0nGp4ss."

# mssql_pid refers to the product key to use. Either:
# - Evaluation
# - Developer
# - Express
# - Web
# - Standard
# - Enterprise
# - A product key (Format: #####-#####-#####-#####-#####)
mssql_pid: Evaluation

# To enable full text search, set this value to yes.
mssql_fts: no

# To update all packages installed by this roles, set `mssql_package_state` to `latest`.
mssql_package_state: present

```

Requirements
------------

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the last 3 release of Ansible.)

The following roles can be installed to ensure all requirements are met, using `ansible-galaxy install -r requirements.yml`:

---
- robertdebock.bootstrap


Context
-------

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/mssql.png "Dependency")


Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|ansible 2.7|ansible devel|
|------------|-----------|-----------|-----------|-----------|-------------|
|alpine-edge*|no|no|no|no|no*|
|alpine-latest|no|no|no|no|no*|
|archlinux|no|no|no|no|no*|
|centos-6|no|no|no|no|no*|
|centos-latest|yes|yes|yes|yes|yes*|
|debian-latest|no|no|no|no|no*|
|debian-stable|no|no|no|no|no*|
|debian-unstable*|no|no|no|no|no*|
|fedora-latest|no|no|no|no|no*|
|fedora-rawhide*|no|no|no|no|no*|
|opensuse-leap|yes|yes|yes|yes|yes*|
|opensuse-tumbleweed|no|no|no|no|no*|
|ubuntu-artful|yes|yes|yes|yes|yes*|
|ubuntu-devel*|no|no|no|no|no*|
|ubuntu-latest|no|no|no|no|no*|

A single star means the build may fail, it's marked as an experimental build.

Testing
-------

[Unit tests](https://travis-ci.org/robertdebock/ansible-role-mssql) are done on every commit and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-mssql/issues)

To test this role locally please use [Molecule](https://github.com/metacloud/molecule):
```
pip install molecule
molecule test
```
There are many specific scenarios available, please have a look in the `molecule/` directory.


License
-------

Apache-2.0


Author Information
------------------

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
