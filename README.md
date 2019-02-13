postgres
=========

Install postgres, optionally move the data dir to custom dir.


Requirements
------------

Target os in ubuntu 16.04 or higher


Role Variables
--------------

Check defaults/main.yml for all variables:

`rootdir` can be changed to a custom dir where data will be moved (say you want
to keep the data in a different mount).

`postgres_version` defaul is 11.

Backups of all databases created are set to be done daily (see
`templates/cronjob_backup.sh`.Log is configure to all queries in
`templates/01log.conf`.


Example Playbook
----------------

    # e.g. if you want to move data to mount other than root device
    - hosts: servers
      tasks:
        - include_role:
            name: ansible-role-postgres
          vars:
            db_data_dir: /mnt/postgres

License
-------

MIT


