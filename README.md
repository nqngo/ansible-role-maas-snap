Role Name
=========

This Ansible role install [https://maas.io/](https://maas.io/) via Ubuntu snaps.

Requirements
------------

- Target hosts: Ubuntu 18.04+ with `snapd` already installed.
- Control host: `ansible~=6`. (Only `ansible==6.5` has been tested)

Role Variables
--------------

```yaml
# MAAS snap channel to use
maas_snap_channel: "3.2/stable"
maas_test_db_channel: "{{ maas_snap_channel }}"

# MAAS local url
maas_url: "http://localhost:5240/MAAS"

# If using an existing postgresql, set this to false
maas_install_test_db: true
# IF using an existing postgresql, set the db uri
maas_db_uri: "maas-test-db:///"

# MAAS admin user name configuration
maas_admin_name: "maas"
maas_admin_password: "maas"
maas_admin_email: "maas@example.com"
```

Dependencies
------------

 - `community.general`

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - role: nqngo.maas_snap
```

License
-------

MIT

Author Information
------------------

For issues, please lodge request at [https://github.com/nqngo/ansible-role-maas-snap/issues](https://github.com/nqngo/ansible-role-maas-snap/issues)
