Ansible Role Template
=========

[![Molecule test](https://github.com/diademiemi/ansible_collection_diademiemi.firefox/actions/workflows/ansible-role-install.yml/badge.svg)](https://github.com/diademiemi/ansible_collection_diademiemi.firefox/actions/workflows/ansible-role-install.yml)

This is an Ansible role to install and configure install.

Include more information about install in this section.

Requirements
------------
These platforms are supported:
- Ubuntu 20.04
- Ubuntu 22.04
- Debian 10
- Debian 11
- Debian 12
- EL 8 (Tested on Rocky Linux 8)
- EL 9 (Tested on Rocky Linux 9)
- Fedora 38
- openSUSE Leap 15.5

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
Variable | Default | Description
---|---|---
`firefox_install_user` | `"{{ ansible_user_id }}"` | User for the Firefox installation, defaults to the Ansible user ID.
`firefox_install_migrate_from_snap` | `true` | Whether to migrate Firefox from a snap installation.
`firefox_install_migrate_data_from_snap` | `true` | Whether to migrate data from the snap installation of Firefox.
`firefox_install_home_dir` | `"{{ lookup('env', 'HOME') }}"` | Home directory for the Firefox installation, defaults to the user's HOME environment variable.
`firefox_install_snap_data_dir` | `"{{ firefox_install_home_dir }}/snap/firefox/common"` | Directory for Firefox snap data, located under the home directory.
`firefox_install_deb_data_dir` | `"{{ firefox_install_home_dir }}"` | Directory for Firefox DEB data, defaults to the home directory.

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
- name: Use diademiemi.firefox.install role
  hosts: "{{ target | default('install') }}"
  roles:
    - role: "diademiemi.firefox.install"
      tags: ['diademiemi', 'install', 'setup']    ```

```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)

Role Testing
------------

This repository comes with Molecule that run in Podman on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.
