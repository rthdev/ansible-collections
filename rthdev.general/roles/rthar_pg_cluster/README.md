Role Name
=========

Configures a postgres basic database cluster

Requirements
------------

- postgresql-server
- python3-psycopg2


Role Variables
--------------

rthar_pg_cluster_manage_disks
  Define if the role should manage the disk device, volume group and filesystem
  Values: [true/false]
  Default: false

rthar_pg_cluster_disk_dev
  Specify the disk device to be used. Will be partitioned with 1 partition, 100% size of device

rthar_pg_cluster_vg_name
  Specify the name of the volume group to be managed

rthar_pg_cluster_lv_name
  Specify the name of the logical volume to be managed

rthar_pg_cluster_lv_fstype
  Specify the filesystem type

rthar_pg_cluster_lv_mntpt
  Specify the mount point of the filesystem

rthar_pg_cluster_name
  Specify the postgres cluster name

rthar_pg_cluster_port
  Specify the postgres cluster port
  Default: 5432


Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: rthar_pg_cluster
          rthar_pg_cluster_disk_dev: /dev/sdb
          rthar_pg_cluster_vg_name: vg_mydb
          rthar_pg_cluster_lv_name: lv_mydb
          rthar_pg_cluster_lv_fstype: xfs
          rthar_pg_cluster_lv_mntpt: /dbs/mydb
          rthar_pg_cluster_name: mydb
          rthar_pg_cluster_port: 5432
          rthar_pg_cluster_manage_disks: true



License
-------

BSD

Author Information
------------------

rth
